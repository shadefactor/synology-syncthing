# synology-syncthing
Scripts and tips for improving the operation of Syncthing on a Synology Diskstation

Syncthing is a cross platform tool for syncing files to other machines in real time. More information is available from the official website <a 
href="https://syncthing.net/" target="_blank">syncthing.net</a>.

Syncthing can be installed from <a href="https://synocommunity.com/" target="_blank">https://synocommunity.com/</a>, but it poses two big problems.

<ul>
	<li>On ds1515 the binary would not run</li>
	<li>The package did not include the syncthing-inotify binary, which watches changes in files.  Without it, every shared directory is periodically 
and fully checked on a schedule.  This is not only a waste of time, but also process intensive.</li>
  
</ul>


To fully appreciate syncthing. Follow these steps. (Mind you, I have tested this on ds1515, and ds412+.  Your data is your data and if it's important to 
you.  You should have backups and test new processes on test data. If you don't take the right precautions and wipe out your data that's your problem.)

<ul>
	<li>Download the appropriate syncthing binary from <a href="https://syncthing.net/" target="_blank">syncthing.net</a>.  Your Synology architecture can be discovered from this page <a href="https://www.synology.com/en-global/knowledgebase/DSM/tutorial/General/What_kind_of_CPU_does_my_NAS_have" target="_blank">What kind of CPU does my NAS have</a></li>
	<li>Copy the syncthing binary over the one in /var/packages/syncthing/target/bin</li>

	<li>Download the appropriate syncthing-inotify binary from <a href="https://github.com/syncthing/syncthing-inotify/releases/latest" 
target="_blank">github</a>.  Again, choose the one for your Synology architecture.</li>
	<li>Copy the syncthing-inotify binary to /var/packages/syncthing/target/bin</li>

	<li>Finally, copy this start-stop-status in this repo to script to /var/packages/syncthing/scripts/</li>
</ul>
