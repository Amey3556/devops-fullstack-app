RUN go mod download

# Copy the rest of the application code into the container
COPY . .

# Build the Go application
RUN go build -o myapp

# Expose the port that your Go application listens on
EXPOSE 8080

# Define environment variables for your PostgreSQL database and allowed origins
ENV DB_HOST <POSTGRES_HOST>
ENV DB_USER <POSTGRES_USER>
ENV DB_PASSWORD <POSTGRES_PASSWORD>
ENV DB_NAME <POSTGRES_DB_NAME>
ENV DB_PORT <POSTGRES_PORT>
ENV ALLOWED_ORIGINS <ALLOWED_ORIGINS_VALUE>

# Start the Go application when the container runs
CMD ["./myapp"]
