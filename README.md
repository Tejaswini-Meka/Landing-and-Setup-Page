# Landing Page
Once the user is logged into any application, what he can see at the first is called "Landing Page"

### Configuration of Landing Page
Setting->user interface->Navigation Menu->default

### Sample XML code
```
<nav search_view="search">
	<view name="search" default='true' />
	<view name="event_count_by_sourcetype" />
	<view name="datasets" />
	<view name="reports" />
	<view name="dashboards" />
</nav>
```
Whatever we have mentioned default=true gonna be the landing page of the application.
If default=true mentioned for other view names, it will consider initial one.

# Setup Page
Useful to store the configurations of the application.</br>
Setup page is onetime flow

### setup Page configuration
Setup page configuration can be done by CLI

### Switch to Splunk User
```
sudo su - splunk
```
### Navigate to Splunk Apps Directory
```
cd /opt/splunk/etc/apps
```
Example: test_app
```
cd test_app
```
App contains the below mentioned folders.
- **appserver**
- **bin**
- **default**
- **local**
- **metadata**

other than default configurations, each configuration shold done under local folder<br>
Local folder contains "app.conf" file</br>
Setup page configuration should done under "app.conf" file</br>

As we didnt configure anything yet, the default stanza will be look like</br>

```
[ui]


[launcher]
```

Add some properties, which will help for Setup page configuration and these things will store in "install" stanza. 

### Edit the existed stanza
```
vi app.conf
```
```
[ui]
setup_view=setup_page

[launcher]

[install]
is configured=false
```
**setup_page** is one of the sample dashboard.

### Restart the Splunk

```
/opt/splunk/bin/splunk restart

