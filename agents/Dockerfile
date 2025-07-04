FROM jenkins/agent:alpine-jdk21

# line from remote - testing confilict manual
# new line from remote

USER root

# Install Python and pip globally
RUN apk add --no-cache python3 py3-pip

# Create a virtual environment
RUN python3 -m venv /opt/venv

# Add venv to PATH temporarily for this build step
# This ensures pip refers to the one inside /opt/venv
ENV PATH="/opt/venv/bin:$PATH"

# Upgrade pip *within the venv* while still root
RUN pip install --upgrade pip

# Now set permissions for the jenkins user
RUN chown -R jenkins:jenkins /opt/venv

# Switch back to the Jenkins user
USER jenkins
