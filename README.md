# Oslo-And-Python-Package-Dependents-for-OpenStack-Kilo-Release
The page lists all Oslo and Python packages dependents needed to build and run OpenStack Kilo release.

The latest OpenStack code Kilo has been scheduled for the late April release this year. Development during this cycle has been focused on making OpenStack rock solid, but there are some new features to keep in mind.

    * Improvements to the upgradability of multiple projects through database changes and objectification
    * More support for Non-Uniform Memory Access (NUMA) in Nova, enabling better memory management and performance
    * Better Neutron network reliability and improved network traffic performance within a cloud with MTU advertisement functionality
    * High Availability improvements through heartbeat monitoring in Oslo, OpenStack's common function library
    * Incremental backups in Cinder
    * Federated user mapping in Keystone, making it easier to manage identities in hybrid environments
    * The ability for Heat to automatically recover from many different types of failures in the environment
    * New metrics and storage methods in Ceilometer

Nova driver for Docker ( i.e. nova-docker) is still the primary integration method to deploy Docker on OpenStack environment however many bug fixed have been introduced in Kilo to make OpenStack-Docker integration less problematic and more stable. Like prior releases, Docker images are stored in Glance and docker format and containers are created using Nova CLI or API. Vendors such as OpneContrail and PlumGrid provided simple plug-in to Docker to interact with Neutron. Kilo release has substantial improvements in Docker integration which include Cinder support, security groups for containers, docker-py and privileged containers.      
       
Kilo Code Release and RPMs

The POC started on Kilo-3 release and will be upgraded to 2015.1 when it becomes available scheduled in late April 2015. All RPMs are compiled from source codes.

    Keystone

        keystone-2015.1.0b3-1.noarch
        python-keystoneclient-1.2.0.post10-1.noarch
        
    Glance

        python-glanceclient-0.17.0-1.noarch
        glance-2015.1.0b3-1.noarch
        
    Nova

        nova-2015.1.0b3-1.noarch
        python-novaclient-2.22.0.post11-1.noarch
        
    Horizon
        horizon-2015.1.0b3-1.noarch
        
    Neutron

        python-neutronclient-2.4.0-1.noarch
        neutron-2015.1.0rc1-1.noarch
        
    Heat


Oslo Dependencies

Oslo is the code name for the general purpose OpenStack Python libraries. Those common libraries are shared among different OpenStack projects to provide a standard code reference and review process. Kilo code depends on following libraries.

    oslo.vmware-0.11.1-1.noarch

    oslo.db-1.7.1-1.noarch:

    oslo.middleware-1.0.0-1.noarch

    oslo.concurrency-1.8.0-1.noarch

    oslo.context-0.2.0-1.noarch

    oslo.i18n-1.5.0-1.noarch

    oslo.messaging-1.8.0-1.noarch

    oslo.policy-0.3.1-1.noarch

    oslo.utils-1.4.0-1.noarch

    oslo.config-1.9.3-1.noarch

    oslo.log-1.0.0-1.noarch

    oslo.serialization-1.4.0-1.noarch


Other Dependencies

Following components are required in order to initiate and run Kilo code, beside the Oslo dependencies listed above.

    Keystone:
        Mysql: all for Openstack configuration data persistence.
            Percona-XtraDB-Cluster-server-56
            Percona-XtraDB-Cluster-client-56
            Percona-XtraDB-Cluster-galera-3
        Memcahed: As the alternative token backend for better token. The default is mysql.
        openstack-utils
        crudini
        sqlalchemy-migrate
        sqlparse
        python-memcached
        keystonemiddleware
        
    Glance:
        Rabbitmq-Server
            Erlang
        retrying
        WSME
        ipaddr
        simplegeneric
        osprofiler
        enum34
        httplib2
        utils
        suds
        python-cinderclient
        glance_store
        python_swiftclient
        keystonemiddleware
        pycrypto
        
    Nova
        python-lxml
        rfc3986
        pyasn1
        psutil
        Jinja2
        cliff
        amqp
        gnutls-utils
        kombu
        MarkupSafe
        
    Horizon
        httpd
        mod_wsgi
        mod_ssl
        
    Neutron
        alembic : A database migration tool for SQLAlchemy.
        Mako:

