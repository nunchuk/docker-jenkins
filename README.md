# docker-jenkins


Sample Jenkin Docker image with some enhancements to official one

* Sets proper permssion for local host volume
* Installs common plugins

- HTML Publisher Plugin - No CSS issue

	http://stackoverflow.com/questions/35783964/jenkins-html-publisher-plugin-no-css-is-displayed-when-report-is-viewed-in-j

	Manage Jenkins->Script console and type in the following command :

	`System.setProperty("hudson.model.DirectoryBrowserSupport.CSP", "")`
