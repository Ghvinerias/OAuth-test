# Build the application from source
FROM golang:1.23 AS build-stage

WORKDIR /app

COPY . .
RUN go mod download
EXPOSE 8080

CMD go run main.go utils.go
# RUN CGO_ENABLED=0 GOOS=linux go build -o /secret-santa

# # Deploy the application binary into a lean image
# FROM alpine AS release-stage

# WORKDIR /

# COPY --from=build-stage /secret-santa /secret-santa

# # Install curl in the alpine image
# RUN apk add --no-cache curl

# HEALTHCHECK --interval=30s --timeout=3s \
#   CMD curl -f http://localhost:8080/healthcheck || exit 1

# ENTRYPOINT ["/secret-santa"]