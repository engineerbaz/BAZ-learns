# RedHat OpenShift

 
Go to [redhat.com/openshift/create/local](url) to download OpenShift Local

<br>

Allocate extra memory to VM by ```crc config set memory 14336 ```
 
enable monitoring ```crc config set enable-cluster-monitoring true```

enable ```crc setup``` to start openshift setup

After setup completes 

<img width="407" height="203" alt="image" src="https://github.com/user-attachments/assets/f511b347-41ed-4360-b09f-2223df507a8d" />


Run ```crc console  --credentials``` to get account details

Run ```crc console``` to open console on webbrowser

--

#### Update OpenShift Local 
- Download lateste
- run `crc delete`
- verify `crc version`
- Run `crc setup`
- Start `crc start`

Git Repo for reference : https://github.com/uguroktay/EX280-Certified-OpenShift-Administrator/tree/main/course_contents