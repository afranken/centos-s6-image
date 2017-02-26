# afranken/centos-s6-image

Image adding the [s6](http://skarnet.org/software/s6/) overlay to the centos base image.

Images inheriting from this image are meant to add `run` scripts to `/etc/services.d/<service_name>` and *not* overwrite the `entrypoint`. 
