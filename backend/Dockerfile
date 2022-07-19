FROM golang:1.18

WORKDIR /usr/src/app

# pre-copy/cache go.mod for pre-downloading dependencies and only redownloading them in subsequent builds if they change
COPY ./src ./
RUN go mod download && go mod verify

# build the program and create an executable called 'backend'
RUN go build -v -o /usr/local/bin/backend ./...

CMD ["backend"]
