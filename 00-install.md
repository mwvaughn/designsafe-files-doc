DesignSafe-CI provides full scriptable access to its underlying infrastructure via the Agave API, which provides a comprehensive set of RESTful web services that make it easy for developers and users to:

* Develop and run applications on HPC, Cloud, Condor, and container-based computing systems
* Use MyProxy-based authentication for federated identity
* Bring their own computing and storage resources into CyVerse
* Share data and applications, even with people who aren't CyVerse users
* Connect computing and data tasks via web-based events
* Manage data on any cloud storage platform one has access to
* Build sophisticated web-based applications that take advantage of all these underlying capabilities

##Initial Assumptions

* You have access to the Designsafe-CI.portal
* You have access to a Linux or Mac OS X commmand-line environment. On Windows, you can work inside a virtual machine configured with any variant of Linux.
* You are comfortable editing text files and working at the command line

##Installing the CLI

The Agave API comes bundled with a set of command line scripts for interacting with it. Using these scripts is generally easier than hand-crafting cURL commands, but if you prefer that route, consult [Getting Started with the Agave API](http://agaveapi.co/getting-started-with-the-agave-api/). All tutorials presented here will assume you are using the command line tools.


On the target system, cd to whatever directory you would like to install the CLI into. We suggest putting it in your HOME directory. Enter the following commands:

```cd $HOME```

or

```cd ~```

Now, clone the {{foundation-cli}} project using {{git}} and add the {{bin}} directory to your {{PATH}}

```
git clone https://bitbucket.org/taccaci/foundation-cli.git agave-cli
export PATH=$PATH:$HOME/agave-cli/bin
```

You may want to make that modification to your PATH permanent by adding this line to your {{.bashrc}} file

```sh
echo "export PATH=\$PATH:\$HOME/agave-cli/bin" >> ~/.bashrc

```

Now, initialize the CLI to work with DesignSafe-Ci

```tenants-init -t designsafe```

You should get this response:

```You are now configured to interact with the APIs at https://agave.designsafe-ci.org/```

*This completes the section on installing the DesignSafe CLI*

[Next: Create an OAuth2 client](00-oauth-101.md)
