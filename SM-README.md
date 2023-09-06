# SM - README

```bash
sudo apt-get install libfontconfig1 fontconfig libfontconfig1-dev
sudo apt-get install libfreetype6 libfreetype6-dev

sudo apt-get install libnss3-dev
sudo apt-get install -y gconf-service libasound2 libatk1.0-0 libc6 libcairo2 libcups2 libdbus-1-3 libexpat1 libfontconfig1 libgcc1 libgconf-2-4 libgdk-pixbuf2.0-0 libglib2.0-0 libgtk-3-0 libnspr4 libpango-1.0-0 libpangocairo-1.0-0 libstdc++6 libx11-6 libx11-xcb1 libxcb1 libxcomposite1 libxcursor1 libxdamage1 libxext6 libxfixes3 libxi6 libxrandr2 libxrender1 libxss1 libxtst6 ca-certificates fonts-liberation libappindicator1 libnss3 lsb-release xdg-utils wget libgbm-dev

npm install pm2 -g
git clone https://github.com/spendmatters-devops/node-export-server
git checkout enhancement/puppeteer
npm install
npm link

n=$(which node); \
n=${n%/bin/node}; \
chmod -R 755 $n/bin/*; \
sudo cp -r $n/{bin,lib,share} /usr/local

cd ~/node-export-server/
sudo pm2 start npm -- start
sudo pm2 list

sudo pm2 logs 0

```
