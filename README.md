# armgen-travis-config

Para configurar o projeto para utilizar a conf:

	before_install:
	- "git clone https://github.com/armgen/armgen-travis-config.git"
	- "cd armgen-travis-config && sh install-custom-repo.sh"

Para adicionar as chaves de segurança:

	travis encrypt REPO_SERVER_USER=deployment --add env.global
	travis encrypt REPO_SERVER_PASSWORD=amz-ARM$1 --add env.global

Exemplo do .travis.yml

```
sudo: false
dist: trusty
language: java
jdk:
- oraclejdk8
services:
- docker
before_install:
- git clone https://github.com/armgen/armgen-travis-config.git
- sh armgen-travis-config/install-custom-repo.sh
install: "./mvnw deploy source:jar javadoc:jar -B -V"
cache:
  directories:
  - "$HOME/.m2"
env:
  global:
  - secure: gL3ulu+vMCZ6zCwMLLCGxRVRweDwJGKhaYFK3Tc6b9IU3Nis+3aEH2xXVyQz75paie0ctx6TPS9Vg+z0gFLAYGlCTw4j9lnsOjqQdapeAxV0wt9UkVXWbZQV8dQ+8GohFRDm63tkmAKgqpJ8tga1iXrg4l5huzaSrGXe+dZOk8a1rBWiunZU/So2aAxP1J3LqkSHknmr3oTh/pY0pzutZUHzqJdmwt/U9ZLftBEDaJCSkmbapaZSQH8FIGfv2GU1Vk6BcOuHU7iB39yr6ywFHLNvY5Jrf20L/FZrE49HcZdDNZX8oJCLNqpAfeWkssPx1wBtP9fJbzla5wQGpYPKu0+9T6J0mWfgm1WxlNep7r3KZLzxILJyT5RsJsjXsvvVD4KeAWG0Bvf/ZlvTv3ncDJns41RLBUGt1KEmTNoEl0KmTImdDc1Ta2DVQ9bBkf2SRx9M+MpehAuNtv+rjU9yoJ1b7jyeSTftSO/Vlf5uvRO/gth9q8A7qDoOevJ50suHOOCBSFFpgRTxinCIo1NpJyz5sgW81ATwGR9cKM1L4iwnKBoWy47Nqcdr7PkSrq2pXE/lCOOPuBSFuG2nInreNgyGKYSvUX9g7B89iv96jkGjbJ1omZuvxVUY2qTpqvOk9Ozv0/x2tYCuFmQjam2QaRsyyOvgLHQfrITtLEjze58=
  - secure: Qme1GfZ+Un5y+df9MOlm4qzrXFCyplEcCWiNSNWUukGJz1rSH72Z2AkJA4PjpOKvPzeevOW5ENZQJv3msO2Or4QKftI2nTf/bCGp7y7Hi7weehb/6sSC2xcW3CUyWGvbPpagJ+70qnplKwU5tpYZZhTW0Q3gFuUvP3gFxq7rNMBbgWHrUvKrBvvJF+2/lkwZ0ZdI5IbCUR8jahRMrvGiXqdiDS17SAc0OMuSBvoRh/JF/QHouERpPCp6OOAbjT9JqjVRbjxo+YusgWQQlWfaf4j2gZeXMuqgRVq8SJvhHrh+DXVMFjjqex9smGW1jGp9CVaCfYfTkFodRBdL88LqFBicYEyZx5q6SY5hJk3R4EOTOJzik/ZqWY2maz7RHTJ2pJgdHZHMFs9FuwHkIca2naVfvrf3WWLZvtQZ0b62fbTcDYGn/V8TONPXNqgMz2gQeaxwKxj9LCe9WMDnn/eZDXApNkzBfnSWuKLT8kvUxEe2HsGswi/17N8ih9LnYOLh1pRKiXIeZx/gY1Z9P89HLlBwbDMbnz/0WMObA9rztpWd4Zp06wTelF9DixSAmicvpxyB1MnSVlwI+PoRDuRhO25ymCjLqYiaywekewFX03IV1uUv7dGSyFmz0uI8Z0eMmrawGTwpt2I5GK8BobhXGBS0EQNxFiPN75414gJdVfY=


```
