var http = require('http'),
	sinaOAuth = require('./lib/sinaOAuth');
	
http.createServer(function (req, res) {
  res.writeHead(200, {'Content-Type': 'text/plain'});
	var sinaoauth = new sinaOAuth();
	sinaoauth.oAuth(req, res, function(error, access_key, access_secret) {
		res.cookie("access_key", access_key);
		res.cookie("access_secret", access_secret);
	});
	var sinaoauth = new sinaOAuth(access_key, access_secret);
	sinaoauth.friends_timeline({}, function(err, data) {
		if (err) return console.log(err);
		res.end(data);
	});
}).listen(1888, "127.0.0.1");
console.log('Server running at http://127.0.0.1:1888/');