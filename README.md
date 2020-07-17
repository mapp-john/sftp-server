# __XFTPD__
## _As a network automation engineer, do you get frustrated at not having instant access to an SFTP/FTP server when you need it most?!_
# Well look no further!
## _Simple, Secure, and Randomized..._
## Right at your fingertips, and ready for API integrations, you have come to the right Python Module!
# XFTPD Server
## SFTP and FTP server Class that can be started and stopped programmatically
## With randomized username, password, RSA keys
## Ideal for on-demand SFTP and FTP and file transfers

## SFTP Example
```python
>>> from ftp_server import SftpServer
>>> SFTP = SftpServer('/tmp',2222)
>>> SFTP.level = 'DEBUG'
>>> SFTP.start()
>>> print(SFTP.Addr)
10.8.2.5
>>> print(SFTP.user)
w7Kg0Fo4Xp6Xo9C
>>> print(SFTP.Pass)
k2Ea0Ko4Rz6Gz3Z
>>>
```

## Example connecting to SFTP server
```bash
[root@CentOS]# sftp -P 2222 w7Kg0Fo4Xp6Xo9C@10.8.2.5
The authenticity of host '[10.8.2.5]:2222 ([10.8.2.5]:2222)' can't be established.
RSA key fingerprint is SHA256:khgoV/GQIShUf4KWr2ZqvpI68KMUFRsedwx4E0hWgi0.
RSA key fingerprint is MD5:d2:45:1b:d8:44:66:5f:66:b9:5e:8d:33:fb:01:0b:b1.
Are you sure you want to continue connecting (yes/no)? yes
Warning: Permanently added '[10.8.2.5]:2222' (RSA) to the list of known hosts.
w7Kg0Fo4Xp6Xo9C@10.8.2.5's password:
Connected to 10.8.2.5.
sftp> dir
new.py                       test.py
sftp> bye
[root@CentOS]#
```

## FTP Example
```python
Python 3.7.4 (default, Sep  7 2019, 18:27:02)
[Clang 10.0.1 (clang-1001.0.46.4)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> from ftp_server import FtpServer
>>> FTP = FtpServer('/tmp')
>>> FTP.start()
[I 2020-07-15 21:14:48] concurrency model: multi-thread
[I 2020-07-15 21:14:48] masquerade (NAT) address: None
[I 2020-07-15 21:14:48] passive ports: None
>>> print(SFTP.Addr)
10.8.2.5
>>> print(FTP.user)
h0Dy0Yq9Ks0Dm3T
>>> print(FTP.Pass)
m5Sg2Yk5Mk8Fa4K
>>>
```

### When the ```stop()``` function is called, the thread will print an Exception to STDOUT, but this will not be an Exception for the codeblock calling the function
```python
>>> Exception in thread Thread-1:
Traceback (most recent call last):
  File "/usr/local/Cellar/python/3.7.4_1/Frameworks/Python.framework/Versions/3.7/lib/python3.7/threading.py", line 926, in _bootstrap_inner
    self.run()
  File "/usr/local/Cellar/python/3.7.4_1/Frameworks/Python.framework/Versions/3.7/lib/python3.7/threading.py", line 870, in run
    self._target(*self._args, **self._kwargs)
  File "/Users/blah/TEMP/ftp_server.py", line 17, in _run_server
    self.SRV.serve_forever()
  File "/usr/local/lib/python3.7/site-packages/pyftpdlib/servers.py", line 478, in serve_forever
    self.ioloop.loop(timeout, blocking)
  File "/usr/local/lib/python3.7/site-packages/pyftpdlib/ioloop.py", line 343, in loop
    poll(timeout)
  File "/usr/local/lib/python3.7/site-packages/pyftpdlib/ioloop.py", line 709, in poll
    timeout)
OSError: [Errno 9] Bad file descriptor

>>>
>>>
```
