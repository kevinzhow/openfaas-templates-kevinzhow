FROM --platform=${TARGETPLATFORM:-linux/amd64} th089/swift:5.4.1-focal as build

WORKDIR /build

COPY . .

RUN swiftc -static-executable function/handler.swift main.swift -o handler

FROM --platform=${TARGETPLATFORM:-linux/amd64} ghcr.io/openfaas/classic-watchdog:0.1.5 as watchdog
FROM --platform=${TARGETPLATFORM:-linux/amd64} alpine:latest

WORKDIR /app
COPY . .

COPY --from=build /build/handler .
RUN chmod +x ./handler

COPY --from=watchdog /fwatchdog ./fwatchdog
RUN chmod +x ./fwatchdog

ENV fprocess="./handler"

HEALTHCHECK --interval=2s CMD [ -e /tmp/.lock ] || exit 1

CMD ["./fwatchdog"]
