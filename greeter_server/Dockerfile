FROM golang:1.23 as builder

WORKDIR /usr/src/app

COPY ./ ./

RUN GOOS=linux GOARCH=amd64 go build -o /usr/local/bin/app ./main.go

FROM scratch

COPY --from=builder /usr/local/bin/app /app
CMD ["/app"]
