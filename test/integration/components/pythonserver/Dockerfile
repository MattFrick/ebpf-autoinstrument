# Dockerfile that will build a container that runs python flask with gunicorn on port 8080
FROM python:3.11.6-slim
EXPOSE 8080
RUN pip install flask gunicorn
# Alternative: RUN pip install flask uwsgi

# Set the working directory to /build
WORKDIR /

# Copy the source code into the image for building
COPY test/integration/components/pythonserver .

CMD ["gunicorn", "-w", "4", "-b", "0.0.0.0:8380", "main:app"]
# CMD uwsgi --http 0.0.0.0:8080 --master -p 4 -w main:app