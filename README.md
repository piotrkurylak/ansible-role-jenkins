## Role Name: Jenkins

Ansible role which allows you to install Jenkins on Debian systems.

## Requirements

None.

## Role Variables

Java versions for Jenkins, switch to 8 or newer than 11 if it is supported.
````yaml
openjdk_supported_version: openjdk-11-jdk
openjdk_nonsupported_versions: [openjdk-7*, openjdk-9*, openjdk-10*, openjdk-12*, openjdk-13*, openjdk-14*, openjdk-15*, openjdk-16*]
````

Switch to weekly release if you want - 'debian' instead of 'debian-stable'
````yaml
jenkins_apt_release_channel: debian-stable
jenkins_repo_url: "https://pkg.jenkins.io/{{ jenkins_apt_release_channel }}"
jenkins_apt_repository: "deb {{ jenkins_repo_url }} binary/"
jenkins_config_file: "/etc/default/jenkins"
````

Change depending on your needs. Default port used by Jenkins is 8080.
````yaml
jenkins_http_port: 8080
````

## Dependencies

None.

## Example Playbook

````yaml
    - hosts: all
      become: yes
      roles:
         - jenkins
````

## License

MIT / BSD

## Author Information

Role created by Piotr Kurylak.
