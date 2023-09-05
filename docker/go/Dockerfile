FROM golang:1.19.1

# Set destination for COPY
WORKDIR /app

# Download Go modules
COPY ./app/go.mod ./app/go.sum ./
RUN go mod download

COPY ./app/*.go ./

# Build
RUN CGO_ENABLED=0 GOOS=linux go build -o /docker-gs-ping

EXPOSE 8989

# Run
CMD [ "/docker-gs-ping" ]

#Назвал имедж go-docker                  docker run --publish 8989:8989 go-docker