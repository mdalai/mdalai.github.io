
### Modify rpm package

To rm a filepath:
- check the filepath: `rpm -qlp /path/to/the.rpm | grep filename`.
- modify rpm with rpmrebuild: `rpmrebuild -enp the.rpm`. Remove the line like `%attr(0555, root, root) "/etc/cron.daily/filename"`. 
Y/N to continue. New RPM should created at $HOME/rpmbuild/RPMS/x86_64/the.rpm
- check again: `rpm -qlp $HOME/rpmbuild/RPMS/x86_64/the.rpm | grep filename`.
- re-do createrepo
