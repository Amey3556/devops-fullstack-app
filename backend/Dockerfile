# Use the official Golang image as the base image
FROM golang:1.19-alpine as build

WORKDIR /app

# Copy the entire application to the working directory
COPY . .

# Build the Golang application
RUN go build -o main .

# Use a smaller base image
FROM alpine:latest

# Set the working directory
WORKDIR /app

# Copy the built binary from the previous stage
COPY --from=build /app/main .

# Expose port 8080
EXPOSE 8080

# Set environment variables
ENV DB_HOST: "52.5.167.154"
ENV DB_USER: "admin"
ENV DB_PASSWORD: "admin"
ENV DB_NAME: "mydb"
ENV DB_PORT: "5432"

# Command to run the Golang application
CMD ["./main"]
