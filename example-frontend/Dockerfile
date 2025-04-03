FROM ubuntu:latest

WORKDIR /usr/src

COPY . .

# Use the recommended ENV format
ENV REACT_APP_BACKEND_URL=http://localhost:8080/

# Update and install required dependencies
RUN apt-get update && apt-get install -y curl gnupg && \
    curl -fsSL https://deb.nodesource.com/setup_16.x | bash && \
    apt-get install -y nodejs && \
    npm install && npm run build && npm install -g serve

CMD ["npx", "serve", "-s", "-l", "5000", "build"]

EXPOSE 5000