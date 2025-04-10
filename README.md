docker build -t html-docker-app .

docker run -d -p 8080:80 html-docker-app


# Use official Nginx image
FROM nginx:alpine

# Remove default Nginx page
RUN rm -rf /usr/share/nginx/html/*

# Copy our HTML file into the web root
COPY index.html /usr/share/nginx/html/

# Expose port 80
EXPOSE 80
