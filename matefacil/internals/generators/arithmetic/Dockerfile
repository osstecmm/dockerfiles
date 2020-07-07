# Using Official Java OpenJDK image
FROM openjdk

# These variables originally are used inside the Django web application.
# They're aiming to be used to generate an arithmetic problem, randomly.
ENV NAME VAR1
ENV NAME VAR2
ENV NAME VAR3
ENV NAME VAR4

# this script is used for internal testing purposes.
COPY run-arithmetic.sh /

# Copy the arithmetic generator code inside the testing container.
# Establish the WORKDIR for the generator.
COPY code /code
WORKDIR /code/

# Compile and execute the generator according to the properties inside
# the MANIFEST.MF file (Java Classpath, etc.)
RUN javac generateRandomArithmetic.java
RUN jar cvmf MANIFEST.MF arithmetic.jar generateRandomArithmetic.class

# Establish the WORKDIR to execute the testing script
WORKDIR /

# This command runs the testing script 
CMD ["/bin/sh", "run-arithmetic.sh"]

