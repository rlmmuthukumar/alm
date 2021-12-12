# AMB Live Monitoring

AMB monitoring listens for contract events and displays them in a nice UI interface.

## Build & test project

```
yarn install
yarn start
```

If you are running a default Ubuntu 18.04 instance you might need to modify the number of 
system monitoring files for React.

```
sudo vi /etc/sysctl.conf
# fs.inotify.max_user_watches=524288
sudo sysctl -p
```

## Heroku deployment

```
heroku create --region eu
git remote -v
heroku config:set NPM_CONFIG_PRODUCTION=false YARN_PRODUCTION=true
git subtree push --prefix alm heroku master
heroku run bash
node scripts/createSnapshots.js
```

Alternatively, you can deploy the monorepo through
https://medium.com/inato/how-to-setup-heroku-with-yarn-workspaces-d8eac0db0256

Do not forget to set the environment variables from `.env` in your Heroku instance.

## References

* [Create React App](https://github.com/facebook/create-react-app)
* [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).
* [React documentation](https://reactjs.org/).
