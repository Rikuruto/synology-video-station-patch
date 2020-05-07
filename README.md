# synology-video-station-patch
解决 Video Station 电影、电视封面无法下载问题

## themoviedb

* 直接修改hosts文件即可

1. 使用 `ssh` 登入
2. `sudo -i` (取得 root 权限)
3. `vi /etc/hosts`
4. 按 `i` 键进入编辑模式
5. 光标移动到最后添加：<br>
13.227.254.58 api.themoviedb.org<br>
13.227.254.109 www.themoviedb.org
6. 按 `Esc` 再输入 `:wq` 保存

## thetvdb

* 修改hosts方式无效，需要外网vps

1. 在vps中运行release中文件
2. 在群晖 `ssh` 中`cd /var/packages/VideoStation/target/plugins/syno_thetvdb`
3. `sed -i 's/http:\/\/IP:19999/https:\/\/www\.thetvdb\.com/g' search.php`
（其中IP为vps的IP）
