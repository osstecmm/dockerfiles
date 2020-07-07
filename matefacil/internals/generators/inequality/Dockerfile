# Using an specific version of GCC image.
FROM gcc:6.5.0

# This variable originally is used inside the Django web application.
# It aims to help to generate an inequality problem, randomly. 
ENV NAME VAR1

# Bring the testing script to the image.
COPY run-comparative.sh /

# Move the generator code inside the image.
COPY code /code

# Establish the working directory.
WORKDIR /code/

# Compile the generator with G++ 
RUN g++ -o generateInequality generateInequality.cpp

# Establish the working directory for the C++ output
WORKDIR /

# Allows to configure a container that will run as an executable.
# In this case we're using a shell script for testing purposes.
ENTRYPOINT ["/run-comparative.sh"]

