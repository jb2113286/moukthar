# Moukthar

Android Remote Administration Tool with C2 Server

## Features
- Hidden App Icon
- Send/Read SMS
- Read Call Log
- Take Picture (Front/Back camera)
- Take Screenshot
- Make Phone Call
- List Installed Apps
- Vibrate Phone
- Change Wallpaper

![Android](https://img.shields.io/badge/Android-00FF00?style=for-the-badge&logo=android&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-FFFFFF?style=for-the-badge&logo=flask&logoColor=black)
![Java](https://img.shields.io/badge/Java-2E8BC0?style=for-the-badge&logo=java&logoColor=white)

## NB
```
USERNAME: android
PASSWORD: android
PEM PASS PHRASE: android
```
Replace the domain value with your ip/domain in ```__init__.py``` wherever you see the line
```python
resp.set_cookie(key="", value="", expires="", domain="your ip/domain")
```
to enable Remember Me functionality in the Login page.

## Production Environment Setup
For linux envitonments, run ```server/setup.sh``` with a privileged user to make moukthar a service.
```console
user@pc1:~/moukthar$ chmod +x ./server/setup.sh
user@pc1:~/moukthar$ sudo ./server/setup.sh
```

### Nginx
```/etc/nginx/sites-available/moukthar```
```nginx
server{
    listen 80;
    server_name moukthar;
    access_log /var/log/nginx/moukthar.access.log;
    error_log /var/log/nginx/moukthar.error.log;

    location / {
       include proxy_params;
       proxy_pass https://127.0.0.1:5001;
    }
}
```

## Warning
THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

