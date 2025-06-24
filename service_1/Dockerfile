FROM golang:1.20-alpine AS builder
WORKDIR /app
COPY go.mod .
COPY main.go .
RUN go build -o service1 .

FROM alpine
WORKDIR /app
COPY --from=builder /app/service1 .
EXPOSE 8001
CMD ["./service1"]