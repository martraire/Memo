#  SSH & SCP

Here are some commands explaning: How to connect to a remote host? or how to copy a file/directory between hosts? 

### SSH: Secure SHell

#### How to connect to a remote machine ?
Let's connect to the remote machine "remotemachine.domain.org"
`ssh user@remotemachine.domain.org`

N.B: Various options are available, the most useful:
`-Y`: Enables trusted X11 forwarding.  Useful for graphic.

#### To make your life easier 
If you are using a lot SSH with different servers, there is a trick to speed up the process:
- Use the file under the **.ssh directory**, should be in your 
home (*/home/me/.ssh/config*). If not, you can create it.
- Specify hosts like this: 
```
Host dev
HostName example.com
User me
```

#### Set up multiple hosts 
Configure several hosts, like previously, this in your configuration file. After you have saved it, you can connect to the host you called **"dev"** by running the following command:
`ssh dev`.



### SCP

#### How to copy a file from your local machine to a remote machine ?
Let's copy a file from the current directory on your local machine to the directory */home/me/stuff* on a remote machine:

`scp myfile user@remotemachine.domain.org:/home/me/stuff`

#### How to copy a file between two remote machines ?
Let's copy a file from remote1 machine to remote2 machine:

`scp user1@remote1:/home/me/file user2@remote2:/home/me/.`

#### How to copy a directory from your local machine to a remote machine ?
Let's copy the directory "mydir" from your local machine to a remote machine "remotemachine.domain.org":

`scp -r mydir user@remotemachine.domain.org:/home/me/.`



### Copy a file with a second remote host

Sometimes, you need to copy a file/directory to a server needing 2 remote hosts. In this case, a simple scp is not enough and we need a two-steps process:
- Open two terminals, where you want to copy your file
- In the first terminal, type:
`ssh -L 1234:remote2:22 -p 22 user1@remote1`
- In the second terminal, type:
`scp -P 1234 user2@localhost:path_file .`

N.B: To copy a directory instead of a file, add `-r` in the third step:
`scp **-r** -P 1234 user2@localhost:path_dir .`

