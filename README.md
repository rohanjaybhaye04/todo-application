Started by user jenkinsuser

java.io.IOException: error=0, Failed to exec spawn helper: pid: 77955, exit value: 1
	at java.base/java.lang.ProcessImpl.forkAndExec(Native Method)
	at java.base/java.lang.ProcessImpl.<init>(ProcessImpl.java:314)
	at java.base/java.lang.ProcessImpl.start(ProcessImpl.java:244)
	at java.base/java.lang.ProcessBuilder.start(ProcessBuilder.java:1110)
Caused: java.io.IOException: Cannot run program "git" (in directory "/var/lib/jenkins/caches/git-ba9b38c483faa6350feac3e31d5455cd"): error=0, Failed to exec spawn helper: pid: 77955, exit value: 1
	at java.base/java.lang.ProcessBuilder.start(ProcessBuilder.java:1143)
	at java.base/java.lang.ProcessBuilder.start(ProcessBuilder.java:1073)
	at hudson.Proc$LocalProc.<init>(Proc.java:252)
	at hudson.Proc$LocalProc.<init>(Proc.java:221)
	at hudson.Launcher$LocalLauncher.launch(Launcher.java:994)
	at hudson.Launcher$ProcStarter.start(Launcher.java:506)
	at PluginClassLoader for git-client//org.jenkinsci.plugins.gitclient.CliGitAPIImpl.launchCommandIn(CliGitAPIImpl.java:2841)
Caused: hudson.plugins.git.GitException: Error performing git command: git init /var/lib/jenkins/caches/git-ba9b38c483faa6350feac3e31d5455cd
	at PluginClassLoader for git-client//org.jenkinsci.plugins.gitclient.CliGitAPIImpl.launchCommandIn(CliGitAPIImpl.java:2864)
	at PluginClassLoader for git-client//org.jenkinsci.plugins.gitclient.CliGitAPIImpl.launchCommandIn(CliGitAPIImpl.java:2768)
	at PluginClassLoader for git-client//org.jenkinsci.plugins.gitclient.CliGitAPIImpl.launchCommandIn(CliGitAPIImpl.java:2763)
	at PluginClassLoader for git-client//org.jenkinsci.plugins.gitclient.CliGitAPIImpl.launchCommand(CliGitAPIImpl.java:2052)
	at PluginClassLoader for git-client//org.jenkinsci.plugins.gitclient.CliGitAPIImpl$5.execute(CliGitAPIImpl.java:1077)
Caused: hudson.plugins.git.GitException: Could not init /var/lib/jenkins/caches/git-ba9b38c483faa6350feac3e31d5455cd
	at PluginClassLoader for git-client//org.jenkinsci.plugins.gitclient.CliGitAPIImpl$5.execute(CliGitAPIImpl.java:1079)
	at PluginClassLoader for git-client//org.jenkinsci.plugins.gitclient.CliGitAPIImpl.init(CliGitAPIImpl.java:359)
	at PluginClassLoader for git-client//hudson.plugins.git.GitAPI.init(GitAPI.java:244)
	at PluginClassLoader for git//jenkins.plugins.git.GitSCMFileSystem$BuilderImpl.build(GitSCMFileSystem.java:390)
Caused: java.io.IOException
	at PluginClassLoader for git//jenkins.plugins.git.GitSCMFileSystem$BuilderImpl.build(GitSCMFileSystem.java:413)
	at PluginClassLoader for scm-api//jenkins.scm.api.SCMFileSystem.of(SCMFileSystem.java:219)
	at PluginClassLoader for workflow-cps//org.jenkinsci.plugins.workflow.cps.CpsScmFlowDefinition.create(CpsScmFlowDefinition.java:126)
	at PluginClassLoader for workflow-cps//org.jenkinsci.plugins.workflow.cps.CpsScmFlowDefinition.create(CpsScmFlowDefinition.java:73)
	at PluginClassLoader for workflow-job//org.jenkinsci.plugins.workflow.job.WorkflowRun.run(WorkflowRun.java:311)
	at hudson.model.ResourceController.execute(ResourceController.java:101)
	at hudson.model.Executor.run(Executor.java:445)
Finished: FAILURE
