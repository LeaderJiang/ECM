#   PostgreSQL安裝及建置手冊
##  查詢[下載頁面](https://www.postgresql.org/download/linux/redhat/ "下載頁面")選擇欲安裝版本
### 1. Install the repository RPM: 
<pre><code>sudo yum install https://download.postgresql.org/pub/repos/yum/11/redhat/rhel-7-x86_64/pgdg-centos11-11-2.noarch.rpm</code></pre>
### 2. Install the client packages:
<pre><code>sudo yum install postgresql11</code></pre>
### 3. Optionally install the server packages:
<pre><code>sudo yum install postgresql11-server</code></pre>
### 4. Optionally initialize the database and enable automatic start:
<pre><code>/usr/pgsql-11/bin/postgresql-11-setup initdb</code></pre>
<pre><code>systemctl enable postgresql-11</code></pre>
<pre><code>systemctl start postgresql-11</code></pre>
### 5. Firewall Setting
<pre><code>firwall-cmd --zone=public --add-port=5432/tcp --permanent</code></pre>
<pre><code>firwall-cmd --reload</code></pre>
<pre><code>firwall-cmd --list-ports</code></pre>
### 6. Password Setting
<pre><code>su - postgres</code></pre>
<pre><code>psql -U postgres</code></pre>
    [SQL]: ALTER USER postgres WITH encrypted PASSWORD '1qaz2wsx';
### 7. Config Setting 
<pre><code>sudo vim /var/lib/pgsql/11/data/postgresql.conf</code></pre>
    [VIM]: listen_addresses = '*'
<pre><code>sudo vim /var/lib/pgsql/11/data/pg_hba.conf</code></pre>
    [VIM]: host     all     all     0.0.0.0/0       md5
<pre><code>systemctl restart postgresql-11</code></pre>
### 8. Change postgres OS Password
<pre><code>passwd postgres...</code></pre>
### 9. Create New PostgreSQL User
<pre><code>createuser --interactive --pwprompt</code></pre>
### 10. Use PostgreSQL to Create User and Database
- Change the user to postgres
    <pre><code>su - postgres</code></pre>
- Create User
    <pre><code>createuser testuser</code></pre>
- Create Database
    <pre><code>createdb testdb</code></pre>
- Provide the privileges to the postgres user
    <pre><code>psql</code></pre>
    <pre><code>[SQL] alter user testuser with encrypted password 'qwerty';</code></pre>
    <pre><code>[SQL] grant all privileges on database testdb to testuser;</code></pre>
## 其他問題：
### 1. postgres is not in the sudoers file.  This incident will be reported.
<pre><code>chmod u+w /etc/sudoers</code></pre>
<pre><code>vim /etc/sudoers</code></pre>
<pre><code>[VIM]: postgres        ALL(ALL)        ALL</code></pre>
<pre><code>chmod u-w /etc/sudoers</code></pre>
### 2. 查詢目前PostgreSQL User 
<pre><code>\du</code></pre>
