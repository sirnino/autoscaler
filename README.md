# Docker Autoscaler

Docker stack that allow a docker SysAdmin to automatically trigger a container scale out accordingly to user-defined rules.

This stack is built up by:

* Google's [cAdvisor](https://github.com/google/cadvisor) - for analyzing resource usage and performance statistics of running containers;
* [Prometheus](https://prometheus.io/) - for obtaining complex metrics based on the cAdvisor performance statistics;
* Sahajsoft's [docker-swarm-service-autoscaler](https://github.com/sahajsoft/docker-swarm-service-autoscaler) - for defining scale-out triggers based on the Prometheus' metrics.

You can find further information about the background tools [here](docs/background.md).

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Prerequisites

Your environment is supposed to be equipped with:

* docker-ce>=18.09.x; [Here](https://docs.docker.com/install/) you can find the instructions for installing Docker CE.
* docker-compose>=1.21.x; [Here](https://docs.docker.com/compose/install/) you can find the instructions for installing docker-compose.

Moreover, your docker daemon must be in SWARM mode. [Here](https://docs.docker.com/engine/swarm/swarm-tutorial/) you can find the instructions for initializing a Docker SWARM.

Do install docker, docker-compose and initialize the swarm, you can also use my [Docker Installer](https://github.com/sirnino/docker-installer).

If everything is ok with your environment you should have the following outputs

```
user@hostname1:~$ docker --version
Docker version 18.09.0, build 4d60db4
```

```
user@hostname1:~$ docker-compose --version
docker-compose version 1.21.2, build a133471
```

If you want to clone the project in order to be alwasys updated with the most recent releases, you also need [git](https://git-scm.com/downloads):

### Installing

The recommended way to obtain the software is cloning the git repository as follows:

```
git clone https://github.com/sirnino/autoscaler.git
```

If you don't have git installed you can download the software from [here](https://github.com/sirnino/autoscaler/archive/master.zip) (note that you won't be able to update the software with the new releases).

You can find more information on how to use the stack in the [usage documentation page](docs/usage.md).

For production environment be sure to disable the internet access to the Prometheus and cAdvisor web GUI.


## Contributing

Please read [CONTRIBUTING.md](CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/sirnino/autoscaler/tags). 

## Authors

* **Antonino Sirchia** - *Initial work* - [sirnino](https://github.com/sirnino)

See also the list of [contributors](https://github.com/sirnino/autoscaler/graphs/contributors) who participated in this project.

## License

This project is licensed under the GNU General Public License v3.0 License - see the [LICENSE.md](LICENSE.md) file for details
