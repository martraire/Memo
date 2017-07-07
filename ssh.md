
      =============================================================
        SSH  - Some commands to connect/copy to a remote server -
      =============================================================
    
                         SSH: Secure SHell 
                         -----------------

    Here are some commands to connect to a remote server using SSH
    Or to copy file from/to a remote server using SCP.
    

    1- SSH 
        
    • To connect on the remote machine "remotemachine.domain.org" :
        > ssh user@remotemachine.domain.org

    N.B: Various options are available, the most useful :
        -Y : Enables trusted X11 forwarding.  Useful for graphic.


    • To make your life easier if using a lot SSH with ≠ servers: 
        - Use the file under the .ssh directory, should be in your 
        home (/home/me/.ssh/config). If not, you can create it.
        - Specify hosts like this: 
            Host pcfarm
            HostName example.com
            User me
        
    • You can set up multiple hosts like this in your configuration 
    file, and after you have saved it, connect to the host you cal-
    -led "pcfarm" by running the following command:
        > ssh dev



    2- SCP

    • To copy a file from the current directory on your local machine 
    to the directory /home/me/stuff on a remote machine : 
        > scp myfile user@remotemachine.domain.org:/home/me/stuff
    
    • To copy a file from remote1 machine to remote2 machine :
        > scp user1@remote1:/home/me/file user2@remote2:/home/me/.
    
    
    • To copy a directory from local machine to a remote machine:
        > scp -r mydir user@remotemachine.domain.org:/home/me/.

    

    3 - Copy a file with a second remote host

    • Open 2 terminals where you want to copy your file 
    (possibly on a second remote host)
    
    • In the first terminal, type:
        > ssh -L 1234:remote2:22 -p 22 user1@remote1
    
    • In the second terminal, type:
        > scp -P 1234 user2@localhost:path_file .














