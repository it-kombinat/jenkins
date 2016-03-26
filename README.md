# jenkins
==========

* Install gems via `gem install`
```	
	rspec-expectations 
	rspec-puppet 
	puppet-lint
	puppetlabs_spec_helper
        rspec 
```
# Install Jenkins - see Jenkins Instruction

 https://wiki.jenkins-ci.org/display/JENKINS/Installing+Jenkins+on+Red+Hat+distributions

# Install Jenkins Plugins

Build Monitor View
Build Pipeline Plugin
Git client plugin
Git plugin
Status Monitor Plugin
Warnings Plugin
# Create Jobs in Jenkins
First create Jobs to test your Modules. For each Test a Job, you can trigger the Next Job.
Set --> Post-build actions Build other projects
* SyntaxCheck with puppet-lint
```
find . -iname *.pp -exec /usr/local/bin/puppet-lint --no-autoloader_layout-check --no-80chars-check --log-format "%{path}:%{line}:%{check}:%{KIND}:%{message}" {} \;
```
* Rspec - Test
```
/usr/local/bin/rake spec
```
After that you must publish the module to the next git repoi/branch.
