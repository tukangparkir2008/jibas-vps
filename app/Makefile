SHELL:=/bin/bash

app_dir=/app
jibas_url=http://www.jibas.net/res/jibas/jibas.education.community.src-26.0.7z
jibas_dir=jibas.education.community-26.0
tmp_dir=/tmp/jibas
archive_file=$(tmp_dir)/jibas.7z
sql_file=$(app_dir)/jibas_db.sql
config_file=$(app_dir)/jibas/include/database.config.php


runsql:
	mysql -u root -p$(DB_ROOT_PASSWORD) -h mysql < $(sql_file)

download-jibas:
	mkdir -p $(tmp_dir)
ifeq ("$(wildcard $(archive_file))","")
	wget -O $(archive_file) $(jibas_url)
endif
	7z x -y -o$(tmp_dir) $(archive_file)
	cp -r $(tmp_dir)/$(jibas_dir)/* /app

clean:
	rm -rf $(tmp_dir)

destroy:
	rm -rf $(app_dir)/jibas $(app_dir)/index.* $(app_dir)/jibas_db.sql $(app_dir)/readme.txt $(app_dir)/filesharing

setting-perms:
	find $(app_dir) -type d -exec chmod 755 {} \;
	find $(app_dir) -type f -exec chmod 644 {} \;
	chmod 777 $(app_dir)/filesharing

config:
	echo "<? \$$db_host='mysql:3306';\$$db_user='root';\$$db_pass='$(DB_ROOT_PASSWORD)';\$$db_name='jbsakad'; ?>" > $(config_file)
	

install: download-jibas setting-perms config runsql clean
