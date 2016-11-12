# CA APM Example for Tomcat in Docker

# Description
This example extension shows how to install a CA APM Java agent in a Tomcat [Docker](http://www.docker.com/) container. along with your application.

For installation instructions, see the README.md file.

# Short Description
This example extension shows how to install a CA APM Java agent to monitor Tomcat running on Docker.

# APM version
CA APM 10.1

# Supported Third Party Versions
Tested with Docker 1.8.2 and 1.9.1.

# License
[Apache 2.0 License]

## Prerequisites
* Install [Docker](http://www.docker.com/).
* Download IntroscopeAgentFiles-NoInstaller<version>tomcat.unix.tar from the [CA Support](http://support.ca.com) and copy it to the Docker build directory.

# Installation

## Install Using CA APM Control Center

### 10.5 

1. Download the bundle (extension) from the CA APM Marketplace.
   http://marketplace.ca.com/shop/ca/?cat=29
2. Go to the Bundles page and click the **Import** button.
2. Navigate to the downloaded bundle and click **Open**.
3. On the Packages page, add the bundle to the desired package.

### 10.2 and 10.3

1. Download the extension (bundle) from the CA APM Marketplace.
   http://marketplace.ca.com/shop/ca/?cat=29
2. Navigate to the downloaded bundle.
3. Copy the bundle to the <APMCommandCenterServer>/import directory. 
   The bundle is automatically imported into the APM Command Center database and moved to the bundles directory.

## Install Manually

### 10.5 and later

1. Download the extension from the CA APM Marketplace.
   http://marketplace.ca.com/shop/ca/?cat=29
2. Navigate to the downloaded extension.
3. Copy the .tar file to the <*Agent_Home*>/extensions/deploy directory.
   The agent automatically automatically installs and deploys the extension, which starts monitoring the managed application.

### 10.3 and earlier

1. Download the extension from the CA APM Marketplace.
   http://marketplace.ca.com/shop/ca/?cat=29
2. Navigate to the downloaded extension and unzip or untar the file as appropriate into the <*Agent_Home*> directory.
3. Copy the extension jar file to the <*Agent_Home*>/core/ext directory.
4. Copy the .pbd or pbl files to the <*Agent_Home*>/core/config directory.
5. Update the IntroscopeAgent.profile file
   * Navigate to <*Agent_Home*>/core/config to update the IntroscopeAgent.profile file.
   * Add the .pbl files to the directives in the IntroscopeAgent.profile.

# Configuration

1. Copy the relevant lines from the supplied [Dockerfile](Dockerfile) into the Dockerfile of your application.
2. In your Dockerfile, set the environment variables ``INTROSCOPE_VERSION`` to the the version of the CA APM Java Agent that you downloaded.
3. Set the environment variables ``EM_HOST``, ``EM_PORT`` to point to your Enterprise Manager and supply an ``AGENT_NAME``. You can do this directly in the Dockerfile when you build the image, from the command line when you start the container or a config file for e.g. [Docker Compose](http://www.docker.com/products/docker-compose).

# Create the Docker Image
Run ``[sudo] docker build -t <image name>``.

# Start a Docker container
Run ``[sudo] docker run [options] <image name>`` or start the container using the tool of your choice.

# Debugging and Troubleshooting
Review the output of the docker build command and the log files inside the container. Connect to the container in interactive mode and run the commands manually from the Dockerfile.

# Support
This document and extension are made available from CA Technologies. They are provided as examples at no charge as a courtesy to the CA APM Community at large. This extension might require modification for use in your environment. However, this extension is not supported by CA Technologies, and inclusion in this site should not be construed to be an endorsement or recommendation by CA Technologies. This extension is not covered by the CA Technologies software license agreement and there is no explicit or implied warranty from CA Technologies. The extension can be used and distributed freely amongst the CA APM Community, but not sold. As such, it is unsupported software, provided as is without warranty of any kind, express or implied, including but not limited to warranties of merchantability and fitness for a particular purpose. CA Technologies does not warrant that this resource will meet your requirements or that the operation of the resource will be uninterrupted or error free or that any defects will be corrected. The use of this extension implies that you understand and agree to the terms listed herein.
Although this extension is unsupported, please let us know if you have any problems or questions. You can add comments to the CA CA APM Community site so that the author(s) can attempt to address the issue or question.
Unless explicitly stated otherwise this extension is only supported on the same platforms as the CA APM Java agent. 

# Support URL
https://github.com/CA-APM-stage/ca-apm-example-docker-tomcat

# Product Compatibilty Matrix
http://pcm.ca.com/

# Categories
Examples, Cloud

# Change Log
Changes for each extension version.

Version | Author | Comment
--------|--------|--------
1.0 | Guenter Grossberger | First version of the extension.