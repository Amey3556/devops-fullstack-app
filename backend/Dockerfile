RUN go mod download

# Copy the rest of the application code into the container
COPY . .

# Build the Go application
RUN go build -o myapp

# Expose the port that your Go application listens on
EXPOSE 8080

# Define environment variables for your PostgreSQL database and allowed origins
ENV DB_HOST=52.5.167.154
ENV DB_USER=admin
ENV DB_PASSWORD=admin
ENV DB_NAME=mydb
ENV DB_PORT=5432
ENV ALLOWED_ORIGINS=*

# Start the Go application when the container runs
CMD ["./myapp"]
