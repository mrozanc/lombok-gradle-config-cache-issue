## Sample project to reproduce delombok issue with configuration cache

### Steps to reproduce
 * Execute
   ```shell
   ./gradlew :delombok --stacktrace
   ```

### Output:
```
Calculating task graph as no cached configuration is available for tasks: :delombok
> Task :generateEffectiveLombokConfig UP-TO-DATE
> Task :delombok UP-TO-DATE

FAILURE: Build failed with an exception.

* What went wrong:
Configuration cache problems found in this build.

1 problem was found storing the configuration cache.
- Task `:delombok` of type `io.freefair.gradle.plugins.lombok.tasks.Delombok`: invocation of 'Task.project' at execution time is unsupported.
  See https://docs.gradle.org/8.7/userguide/configuration_cache.html#config_cache:requirements:use_project_during_execution

See the complete report at file:///xxx/lombok-gradle-config-cache-issue/build/reports/configuration-cache/3kkdy8b8o2xfnje9mo5jvgzqu/89saw3qk3rl7382b7ys1vjhpl/configuration-cache-report.html
> Invocation of 'Task.project' by task ':delombok' at execution time is unsupported.

* Try:
> Run with --info or --debug option to get more log output.
> Run with --scan to get full insights.
> Get more help at https://help.gradle.org.

* Exception is:
org.gradle.configurationcache.ConfigurationCacheProblemsException: Configuration cache problems found in this build.

1 problem was found storing the configuration cache.
- Task `:delombok` of type `io.freefair.gradle.plugins.lombok.tasks.Delombok`: invocation of 'Task.project' at execution time is unsupported.
  See https://docs.gradle.org/8.7/userguide/configuration_cache.html#config_cache:requirements:use_project_during_execution

See the complete report at file:///xxx/lombok-gradle-config-cache-issue/build/reports/configuration-cache/3kkdy8b8o2xfnje9mo5jvgzqu/89saw3qk3rl7382b7ys1vjhpl/configuration-cache-report.html
	at org.gradle.configurationcache.problems.ConfigurationCacheProblems.queryFailure(ConfigurationCacheProblems.kt:149)
	at org.gradle.configurationcache.problems.ConfigurationCacheProblems.report(ConfigurationCacheProblems.kt:177)
	at org.gradle.internal.buildtree.ProblemReportingBuildActionRunner.reportProblems(ProblemReportingBuildActionRunner.java:61)
	at org.gradle.internal.buildtree.ProblemReportingBuildActionRunner.run(ProblemReportingBuildActionRunner.java:52)
	at org.gradle.launcher.exec.BuildOutcomeReportingBuildActionRunner.run(BuildOutcomeReportingBuildActionRunner.java:65)
	at org.gradle.tooling.internal.provider.FileSystemWatchingBuildActionRunner.run(FileSystemWatchingBuildActionRunner.java:140)
	at org.gradle.launcher.exec.BuildCompletionNotifyingBuildActionRunner.run(BuildCompletionNotifyingBuildActionRunner.java:41)
	at org.gradle.launcher.exec.RootBuildLifecycleBuildActionExecutor.lambda$execute$0(RootBuildLifecycleBuildActionExecutor.java:40)
	at org.gradle.composite.internal.DefaultRootBuildState.run(DefaultRootBuildState.java:123)
	at org.gradle.launcher.exec.RootBuildLifecycleBuildActionExecutor.execute(RootBuildLifecycleBuildActionExecutor.java:40)
	at org.gradle.internal.buildtree.InitDeprecationLoggingActionExecutor.execute(InitDeprecationLoggingActionExecutor.java:66)
	at org.gradle.internal.buildtree.InitProblems.execute(InitProblems.java:36)
	at org.gradle.internal.buildtree.DefaultBuildTreeContext.execute(DefaultBuildTreeContext.java:40)
	at org.gradle.launcher.exec.BuildTreeLifecycleBuildActionExecutor.lambda$execute$0(BuildTreeLifecycleBuildActionExecutor.java:71)
	at org.gradle.internal.buildtree.BuildTreeState.run(BuildTreeState.java:60)
	at org.gradle.launcher.exec.BuildTreeLifecycleBuildActionExecutor.execute(BuildTreeLifecycleBuildActionExecutor.java:71)
	at org.gradle.launcher.exec.RunAsBuildOperationBuildActionExecutor$3.call(RunAsBuildOperationBuildActionExecutor.java:61)
	at org.gradle.launcher.exec.RunAsBuildOperationBuildActionExecutor$3.call(RunAsBuildOperationBuildActionExecutor.java:57)
	at org.gradle.internal.operations.DefaultBuildOperationRunner$CallableBuildOperationWorker.execute(DefaultBuildOperationRunner.java:200)
	at org.gradle.internal.operations.DefaultBuildOperationRunner$CallableBuildOperationWorker.execute(DefaultBuildOperationRunner.java:195)
	at org.gradle.internal.operations.DefaultBuildOperationRunner$2.execute(DefaultBuildOperationRunner.java:66)
	at org.gradle.internal.operations.DefaultBuildOperationRunner$2.execute(DefaultBuildOperationRunner.java:59)
	at org.gradle.internal.operations.DefaultBuildOperationRunner.execute(DefaultBuildOperationRunner.java:157)
	at org.gradle.internal.operations.DefaultBuildOperationRunner.execute(DefaultBuildOperationRunner.java:59)
	at org.gradle.internal.operations.DefaultBuildOperationRunner.call(DefaultBuildOperationRunner.java:53)
	at org.gradle.internal.operations.DefaultBuildOperationExecutor.call(DefaultBuildOperationExecutor.java:73)
	at org.gradle.launcher.exec.RunAsBuildOperationBuildActionExecutor.execute(RunAsBuildOperationBuildActionExecutor.java:57)
	at org.gradle.launcher.exec.RunAsWorkerThreadBuildActionExecutor.lambda$execute$0(RunAsWorkerThreadBuildActionExecutor.java:36)
	at org.gradle.internal.work.DefaultWorkerLeaseService.withLocks(DefaultWorkerLeaseService.java:264)
	at org.gradle.internal.work.DefaultWorkerLeaseService.runAsWorkerThread(DefaultWorkerLeaseService.java:128)
	at org.gradle.launcher.exec.RunAsWorkerThreadBuildActionExecutor.execute(RunAsWorkerThreadBuildActionExecutor.java:36)
	at org.gradle.tooling.internal.provider.continuous.ContinuousBuildActionExecutor.execute(ContinuousBuildActionExecutor.java:110)
	at org.gradle.tooling.internal.provider.SubscribableBuildActionExecutor.execute(SubscribableBuildActionExecutor.java:64)
	at org.gradle.internal.session.DefaultBuildSessionContext.execute(DefaultBuildSessionContext.java:46)
	at org.gradle.tooling.internal.provider.BuildSessionLifecycleBuildActionExecuter$ActionImpl.apply(BuildSessionLifecycleBuildActionExecuter.java:92)
	at org.gradle.tooling.internal.provider.BuildSessionLifecycleBuildActionExecuter$ActionImpl.apply(BuildSessionLifecycleBuildActionExecuter.java:80)
	at org.gradle.internal.session.BuildSessionState.run(BuildSessionState.java:71)
	at org.gradle.tooling.internal.provider.BuildSessionLifecycleBuildActionExecuter.execute(BuildSessionLifecycleBuildActionExecuter.java:62)
	at org.gradle.tooling.internal.provider.BuildSessionLifecycleBuildActionExecuter.execute(BuildSessionLifecycleBuildActionExecuter.java:41)
	at org.gradle.tooling.internal.provider.StartParamsValidatingActionExecuter.execute(StartParamsValidatingActionExecuter.java:64)
	at org.gradle.tooling.internal.provider.StartParamsValidatingActionExecuter.execute(StartParamsValidatingActionExecuter.java:32)
	at org.gradle.tooling.internal.provider.SessionFailureReportingActionExecuter.execute(SessionFailureReportingActionExecuter.java:51)
	at org.gradle.tooling.internal.provider.SessionFailureReportingActionExecuter.execute(SessionFailureReportingActionExecuter.java:39)
	at org.gradle.tooling.internal.provider.SetupLoggingActionExecuter.execute(SetupLoggingActionExecuter.java:47)
	at org.gradle.tooling.internal.provider.SetupLoggingActionExecuter.execute(SetupLoggingActionExecuter.java:31)
	at org.gradle.launcher.daemon.server.exec.ExecuteBuild.doBuild(ExecuteBuild.java:65)
	at org.gradle.launcher.daemon.server.exec.BuildCommandOnly.execute(BuildCommandOnly.java:37)
	at org.gradle.launcher.daemon.server.api.DaemonCommandExecution.proceed(DaemonCommandExecution.java:104)
	at org.gradle.launcher.daemon.server.exec.WatchForDisconnection.execute(WatchForDisconnection.java:39)
	at org.gradle.launcher.daemon.server.api.DaemonCommandExecution.proceed(DaemonCommandExecution.java:104)
	at org.gradle.launcher.daemon.server.exec.ResetDeprecationLogger.execute(ResetDeprecationLogger.java:29)
	at org.gradle.launcher.daemon.server.api.DaemonCommandExecution.proceed(DaemonCommandExecution.java:104)
	at org.gradle.launcher.daemon.server.exec.RequestStopIfSingleUsedDaemon.execute(RequestStopIfSingleUsedDaemon.java:35)
	at org.gradle.launcher.daemon.server.api.DaemonCommandExecution.proceed(DaemonCommandExecution.java:104)
	at org.gradle.launcher.daemon.server.exec.ForwardClientInput$2.create(ForwardClientInput.java:78)
	at org.gradle.launcher.daemon.server.exec.ForwardClientInput$2.create(ForwardClientInput.java:75)
	at org.gradle.util.internal.Swapper.swap(Swapper.java:38)
	at org.gradle.launcher.daemon.server.exec.ForwardClientInput.execute(ForwardClientInput.java:75)
	at org.gradle.launcher.daemon.server.api.DaemonCommandExecution.proceed(DaemonCommandExecution.java:104)
	at org.gradle.launcher.daemon.server.exec.LogAndCheckHealth.execute(LogAndCheckHealth.java:64)
	at org.gradle.launcher.daemon.server.api.DaemonCommandExecution.proceed(DaemonCommandExecution.java:104)
	at org.gradle.launcher.daemon.server.exec.LogToClient.doBuild(LogToClient.java:63)
	at org.gradle.launcher.daemon.server.exec.BuildCommandOnly.execute(BuildCommandOnly.java:37)
	at org.gradle.launcher.daemon.server.api.DaemonCommandExecution.proceed(DaemonCommandExecution.java:104)
	at org.gradle.launcher.daemon.server.exec.EstablishBuildEnvironment.doBuild(EstablishBuildEnvironment.java:84)
	at org.gradle.launcher.daemon.server.exec.BuildCommandOnly.execute(BuildCommandOnly.java:37)
	at org.gradle.launcher.daemon.server.api.DaemonCommandExecution.proceed(DaemonCommandExecution.java:104)
	at org.gradle.launcher.daemon.server.exec.StartBuildOrRespondWithBusy$1.run(StartBuildOrRespondWithBusy.java:52)
	at org.gradle.launcher.daemon.server.DaemonStateCoordinator$1.run(DaemonStateCoordinator.java:297)
	at org.gradle.internal.concurrent.ExecutorPolicy$CatchAndRecordFailures.onExecute(ExecutorPolicy.java:64)
	at org.gradle.internal.concurrent.AbstractManagedExecutor$1.run(AbstractManagedExecutor.java:47)
Caused by: org.gradle.api.InvalidUserCodeException: Invocation of 'Task.project' by task ':delombok' at execution time is unsupported.
	at org.gradle.configurationcache.problems.DefaultProblemFactory$problem$1$build$diagnostics$1.get(DefaultProblemFactory.kt:79)
	at org.gradle.configurationcache.problems.DefaultProblemFactory$problem$1$build$diagnostics$1.get(DefaultProblemFactory.kt:79)
	at org.gradle.internal.problems.DefaultProblemDiagnosticsFactory$DefaultProblemStream.getImplicitThrowable(DefaultProblemDiagnosticsFactory.java:150)
	at org.gradle.internal.problems.DefaultProblemDiagnosticsFactory$DefaultProblemStream.forCurrentCaller(DefaultProblemDiagnosticsFactory.java:139)
	at org.gradle.configurationcache.problems.DefaultProblemFactory$problem$1.build(DefaultProblemFactory.kt:79)
	at org.gradle.configurationcache.initialization.DefaultConfigurationCacheProblemsListener.onTaskExecutionAccessProblem(ConfigurationCacheProblemsListener.kt:134)
	at org.gradle.configurationcache.initialization.DefaultConfigurationCacheProblemsListener.onProjectAccess(ConfigurationCacheProblemsListener.kt:74)
	at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
	at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
	at java.base/jdk.internal.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
	at org.gradle.internal.dispatch.ReflectionDispatch.dispatch(ReflectionDispatch.java:36)
	at org.gradle.internal.dispatch.ReflectionDispatch.dispatch(ReflectionDispatch.java:24)
	at org.gradle.internal.event.DefaultListenerManager$ListenerDetails.dispatch(DefaultListenerManager.java:472)
	at org.gradle.internal.event.DefaultListenerManager$ListenerDetails.dispatch(DefaultListenerManager.java:454)
	at org.gradle.internal.event.AbstractBroadcastDispatch.dispatch(AbstractBroadcastDispatch.java:83)
	at org.gradle.internal.event.AbstractBroadcastDispatch.dispatch(AbstractBroadcastDispatch.java:69)
	at org.gradle.internal.event.DefaultListenerManager$EventBroadcast$ListenerDispatch.dispatch(DefaultListenerManager.java:443)
	at org.gradle.internal.event.DefaultListenerManager$EventBroadcast$ListenerDispatch.dispatch(DefaultListenerManager.java:431)
	at org.gradle.internal.event.AbstractBroadcastDispatch.dispatch(AbstractBroadcastDispatch.java:43)
	at org.gradle.internal.event.AbstractBroadcastDispatch.dispatch(AbstractBroadcastDispatch.java:66)
	at org.gradle.internal.event.DefaultListenerManager$EventBroadcast$ListenerDispatch.dispatch(DefaultListenerManager.java:443)
	at org.gradle.internal.event.DefaultListenerManager$EventBroadcast.dispatch(DefaultListenerManager.java:232)
	at org.gradle.internal.event.DefaultListenerManager$EventBroadcast.dispatch(DefaultListenerManager.java:203)
	at org.gradle.internal.dispatch.ProxyDispatchAdapter$DispatchingInvocationHandler.invoke(ProxyDispatchAdapter.java:94)
	at com.sun.proxy.$Proxy97.onProjectAccess(Unknown Source)
	at org.gradle.configurationcache.AbstractTaskProjectAccessChecker.notifyProjectAccess(TaskExecutionAccessCheckers.kt:33)
	at org.gradle.api.internal.AbstractTask.getProject(AbstractTask.java:238)
	at org.gradle.api.DefaultTask.getProject(DefaultTask.java:59)
	at io.freefair.gradle.plugins.lombok.tasks.Delombok.getFilteredInput(Delombok.java:137)
	at io.freefair.gradle.plugins.lombok.tasks.Delombok_Decorated.getFilteredInput(Unknown Source)
	at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
	at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
	at java.base/jdk.internal.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
	at org.gradle.internal.reflect.annotations.impl.DefaultPropertyAnnotationMetadata.getPropertyValue(DefaultPropertyAnnotationMetadata.java:97)
	at org.gradle.internal.properties.annotations.DefaultTypeMetadataStore$DefaultPropertyMetadata.getPropertyValue(DefaultTypeMetadataStore.java:284)
	at org.gradle.internal.properties.bean.DefaultPropertyWalker$1.lambda$visitLeaf$0(DefaultPropertyWalker.java:90)
	at org.gradle.internal.deprecation.DeprecationLogger.whileDisabled(DeprecationLogger.java:259)
	at org.gradle.internal.properties.bean.DefaultPropertyWalker$CachedPropertyValue.lambda$new$0(DefaultPropertyWalker.java:107)
	at com.google.common.base.Suppliers$NonSerializableMemoizingSupplier.get(Suppliers.java:181)
	at org.gradle.internal.properties.bean.DefaultPropertyWalker$CachedPropertyValue.call(DefaultPropertyWalker.java:149)
	at org.gradle.api.internal.tasks.properties.DefaultFinalizingValidatingProperty.prepareValue(DefaultFinalizingValidatingProperty.java:33)
	at org.gradle.api.internal.tasks.execution.FinalizePropertiesTaskExecuter.execute(FinalizePropertiesTaskExecuter.java:43)
	at org.gradle.api.internal.tasks.execution.ResolveTaskExecutionModeExecuter.execute(ResolveTaskExecutionModeExecuter.java:51)
	at org.gradle.api.internal.tasks.execution.SkipTaskWithNoActionsExecuter.execute(SkipTaskWithNoActionsExecuter.java:57)
	at org.gradle.api.internal.tasks.execution.SkipOnlyIfTaskExecuter.execute(SkipOnlyIfTaskExecuter.java:74)
	at org.gradle.api.internal.tasks.execution.CatchExceptionTaskExecuter.execute(CatchExceptionTaskExecuter.java:36)
	at org.gradle.api.internal.tasks.execution.EventFiringTaskExecuter$1.executeTask(EventFiringTaskExecuter.java:77)
	at org.gradle.api.internal.tasks.execution.EventFiringTaskExecuter$1.call(EventFiringTaskExecuter.java:55)
	at org.gradle.api.internal.tasks.execution.EventFiringTaskExecuter$1.call(EventFiringTaskExecuter.java:52)
	at org.gradle.internal.operations.DefaultBuildOperationRunner$CallableBuildOperationWorker.execute(DefaultBuildOperationRunner.java:200)
	at org.gradle.internal.operations.DefaultBuildOperationRunner$CallableBuildOperationWorker.execute(DefaultBuildOperationRunner.java:195)
	at org.gradle.internal.operations.DefaultBuildOperationRunner$2.execute(DefaultBuildOperationRunner.java:66)
	at org.gradle.internal.operations.DefaultBuildOperationRunner$2.execute(DefaultBuildOperationRunner.java:59)
	at org.gradle.internal.operations.DefaultBuildOperationRunner.execute(DefaultBuildOperationRunner.java:157)
	at org.gradle.internal.operations.DefaultBuildOperationRunner.execute(DefaultBuildOperationRunner.java:59)
	at org.gradle.internal.operations.DefaultBuildOperationRunner.call(DefaultBuildOperationRunner.java:53)
	at org.gradle.internal.operations.DefaultBuildOperationExecutor.call(DefaultBuildOperationExecutor.java:73)
	at org.gradle.api.internal.tasks.execution.EventFiringTaskExecuter.execute(EventFiringTaskExecuter.java:52)
	at org.gradle.execution.plan.LocalTaskNodeExecutor.execute(LocalTaskNodeExecutor.java:42)
	at org.gradle.execution.taskgraph.DefaultTaskExecutionGraph$InvokeNodeExecutorsAction.execute(DefaultTaskExecutionGraph.java:331)
	at org.gradle.execution.taskgraph.DefaultTaskExecutionGraph$InvokeNodeExecutorsAction.execute(DefaultTaskExecutionGraph.java:318)
	at org.gradle.execution.taskgraph.DefaultTaskExecutionGraph$BuildOperationAwareExecutionAction.lambda$execute$0(DefaultTaskExecutionGraph.java:314)
	at org.gradle.internal.operations.CurrentBuildOperationRef.with(CurrentBuildOperationRef.java:80)
	at org.gradle.execution.taskgraph.DefaultTaskExecutionGraph$BuildOperationAwareExecutionAction.execute(DefaultTaskExecutionGraph.java:314)
	at org.gradle.execution.taskgraph.DefaultTaskExecutionGraph$BuildOperationAwareExecutionAction.execute(DefaultTaskExecutionGraph.java:303)
	at org.gradle.execution.plan.DefaultPlanExecutor$ExecutorWorker.execute(DefaultPlanExecutor.java:463)
	at org.gradle.execution.plan.DefaultPlanExecutor$ExecutorWorker.run(DefaultPlanExecutor.java:380)
	at org.gradle.internal.concurrent.ExecutorPolicy$CatchAndRecordFailures.onExecute(ExecutorPolicy.java:64)
	at org.gradle.internal.concurrent.AbstractManagedExecutor$1.run(AbstractManagedExecutor.java:47)


BUILD FAILED in 566ms
2 actionable tasks: 2 up-to-date
Configuration cache entry discarded with 1 problem.
```

### From configuration cache HTML report
```
Storing the configuration cache for :delombok
10 build configuration inputs were found and will cause the cache to be discarded when their value change
1 problem was found
Build configuration inputs10
Problems grouped by message1
Problems grouped by location1

    ⌄ ⨉invocation of Task.project

at execution time is unsupported. ?

    ⌄ task:delombok

of type io.freefair.gradle.plugins.lombok.tasks.Delombok
⌄ Exception
at io.freefair.gradle.plugins.lombok.tasks.Delombok.getFilteredInput(Delombok.java:137)

    org.gradle.api.InvalidUserCodeException: Invocation of 'Task.project' by task ':delombok' at execution time is unsupported.

    	at org.gradle.api.DefaultTask.getProject(DefaultTask.java:59)

    	at io.freefair.gradle.plugins.lombok.tasks.Delombok.getFilteredInput(Delombok.java:137)
    	at io.freefair.gradle.plugins.lombok.tasks.Delombok_Decorated.getFilteredInput(Unknown Source)

    	at org.gradle.internal.properties.bean.DefaultPropertyWalker$CachedPropertyValue.lambda$new$0(DefaultPropertyWalker.java:107)

    	at com.google.common.base.Suppliers$NonSerializableMemoizingSupplier.get(Suppliers.java:181)

    	at java.base/java.lang.Thread.run(Thread.java:829)
```