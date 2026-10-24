
FROM golang:1.16

WORKDIR /usr/src/app

# Copy the source code into the container
COPY . .

# Compile the Go backend
RUN go build -o server

# Configure the application port
ENV PORT=8080

EXPOSE 8080

# Start the server
CMD ["./server"]
