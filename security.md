# Hardening Security Measures

## AppArmor security profiles for Docker 

When you run a container, it uses the **docker-default** policy. Use **security-opt** to override the default:  
```bash
docker run --rm -it --security-opt apparmor=docker-default todo-app

# load new profile
$ apparmor_parser -r -W /path/to/your_profile

# run with new profile
docker run --rm -it --security-opt apparmor=your_profile hello-world

# unload the profile
$ apparmor_parser -R /path/to/profile
```

## Resources
1. https://docs.docker.com/engine/security/apparmor/ 
2. https://www.stackrox.com/post/2017/08/hardening-docker-containers-and-hosts-against-vulnerabilities-a-security-toolkit/
3. 
