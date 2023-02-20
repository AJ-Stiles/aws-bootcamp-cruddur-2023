FROM python:3.10-slim-buster

# inside container
# make a new folder inside the container
WORKDIR /backend-flask

# outside container -> inside container
# this contains the required libaries we want to install to run the app
COPY requirements.txt requirements.txt

# inside the container
# this installs the python libaries used for the app
RUN pip3 install -r requirements.txt

# outside container -> inside container
# . means everything in the current directory
# first period - /backend-flask (outside container)
# second period - /backend-flask (inside container)
COPY . .

# set environment variables(env vars)
# Inside container and will remain set when the container is running
ENV FLASK_ENV=development

EXPOSE ${PORT}
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]