# apache_django
#instructions to install apache and djagno on aws linux 2

sudo yum install gcc openssl-devel bzip2-devel libffi-devel zlib-devel httpd httpd-devel  
cd /usr/src  
sudo wget https://www.python.org/ftp/python/3.7.9/Python-3.7.9.tgz  
sudo tar zxvf Python-3.7.9.tgz   
cd Python-3.7.9  
sudo ./configure --enable-shared --enable-optimizations  

sudo make  
sudo make altinstall  
sudo ldconfig /usr/local/lib   

python3.7 --version  
cd /var/www/  
sudo mkdir django  
sudo chown ec2-user django  
python3.7 -m venv venv  
source venv/bin/activate  

pip install mod_wsgi  
  
#install all other packaged in requirements.txt file  
#copy djagno.conf file to /etc/httpd/conf.d/  
sudo nano /etc/httpd/conf.d/django.conf  
sudo systemctl restart httpd  
sudo systemctl enable httpd   
