# Cloudera Manager Server Startup log

```

[root@ip-172-31-28-237 yum.repos.d]# tail -f /var/log/cloudera-scm-server/cloudera-scm-server.log
2018-05-17 08:49:18,526 INFO SearchRepositoryManager-0:com.cloudera.server.web.cmf.search.components.SearchRepositoryManager: Generating entities:2018-05-17T08:49:18.525Z
2018-05-17 08:49:18,536 INFO SearchRepositoryManager-0:com.cloudera.server.web.cmf.search.components.SearchRepositoryManager: Num entities:205
2018-05-17 08:49:18,536 INFO SearchRepositoryManager-0:com.cloudera.server.web.cmf.search.components.SearchRepositoryManager: Generating documents:2018-05-17T08:49:18.536Z
2018-05-17 08:49:18,563 INFO SearchRepositoryManager-0:com.cloudera.server.web.cmf.search.components.SearchRepositoryManager: Num docs:218
2018-05-17 08:49:18,567 INFO SearchRepositoryManager-0:com.cloudera.server.web.cmf.search.components.SearchRepositoryManager: Constructing repo:2018-05-17T08:49:18.567Z
2018-05-17 08:49:19,577 INFO SearchRepositoryManager-0:com.cloudera.server.web.cmf.search.components.SearchRepositoryManager: Finished constructing repo:2018-05-17T08:49:19.577Z
2018-05-17 08:49:19,783 INFO WebServerImpl:org.mortbay.log: jetty-6.1.26.cloudera.4
2018-05-17 08:49:19,784 INFO WebServerImpl:org.mortbay.log: Started SelectChannelConnector@0.0.0.0:7180
2018-05-17 08:49:19,784 INFO WebServerImpl:com.cloudera.server.cmf.WebServerImpl: Started Jetty server.
2018-05-17 08:49:22,082 INFO ScmActive-0:com.cloudera.server.cmf.components.ScmActive: ScmActive completed successfully.

```