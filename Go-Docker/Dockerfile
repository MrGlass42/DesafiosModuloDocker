FROM golang as Builder

WORKDIR /app

COPY ./volume .

RUN go build program.go

RUN rm program.go

FROM scratch

COPY --from=Builder /app/program .

ENTRYPOINT ["./program"]