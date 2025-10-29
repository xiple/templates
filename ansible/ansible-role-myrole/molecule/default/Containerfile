FROM registry.fedoraproject.org/fedora:42

ENV pip_packages="ansible"

# Install requirements.
# python3-libdnf5 for ansible.builtin.dnf module
# python3-rpm for ansible.builtin.package_facts module

RUN dnf -y upgrade \
    && dnf -y install python3 python3-pip python3-libdnf5 python3-rpm \
    && dnf clean all

# Upgrading pip
RUN python3 -m pip install --upgrade pip

# Install Ansible via Pip.
RUN python3 -m pip install $pip_packages

# Run the command
CMD ["/bin/bash"]
