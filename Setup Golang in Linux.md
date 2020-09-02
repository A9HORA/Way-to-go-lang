# Golang installation in ubuntu(debian)
### Note: During this docmentation latest and stable version of golang was 1.15.1. If you are reading this then please check the latest and stable one at https://golang.org/dl/

1. Identify your **linux kernel architecture**  
	`uname -m` or `arch`  
  
2. Choose directory for downloading and saving the file. I'm using `/opt/`  
	 `cd /opt/`  
   
3. Choose the latest stable package as per your architecture and download it with wget.  
	 `wget https://golang.org/dl/go1.15.1.linux-amd64.tar.gz`  
   
4. Let's check type of compression applied on downloaded file so we can use valid command to extract it.  
	 `file go1.15.1.linux-amd64.tar.gz`  
   In my case it shows gzip compressed data so I can use tar to extract it.  
   
5. Time to extract files  
	 `tar -xvf go1.15.1.linux-amd64.tar.gz`  
   
6. I'm changing ownership and moving it to `/usr/local` which is **officially recommended location.**  
	 `chown -R root:root go/`  
	 `mv go/ /usr/local/`  
   
7. We need to **set path of golang so we can use it as system command.**  
	 `vi ~/.profile`  
   
8. Go to **end of the file** then `press I` to get in insertion mode.  

9. Add below mentioned lined at the end of this file.  
	 `export GOPATH=$HOME/work`  
	 `export PATH=$PATH:/usr/local/go/bin:$GOPATH/bin`  
   
10. `Press ESC` and type `:wq` for **saving the changes.**  

11. We have to **refresh the /.profile file for reflecting the changes.**  
	  `source ~/.profile`  
    
12. Let's check the installation.  
	  `go version`
