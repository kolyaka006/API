var restify = require('restify');

var server = restify.createServer();

server.use(restify.bodyParser());

server.post('/endpoint/post_response', function (req, res, next) {
    if(req.params.request == "error") {res.send(204)}
    if(req.params.request) {res.send(200,{body:"Successfully recieved data from user."})}
    res.send(204);
    return next();
});

server.get('/endpoint/response_codes', function (req, res, next) {
    var numb =  Math.floor(Math.random() * (100)%2);
    if(numb) {
        res.send(200,{result:true,text:"Success!"})
    } else {
        res.send(200,{result:false,text:"Failure!"})
    }
    return next();
});

server.get('/endpoint/data_set', function (req, res, next) {
    var numb =  Math.floor(Math.random() * (100)%2);
    if(numb) {
        var plant =  Math.floor(Math.random() * (100)%3);
        switch (plant) {
            case 0: res.send(200,{item: "apple", type: "fruit"})
            case 1: res.send(200,{item: "pear", type: "fruit"})
            case 2: res.send(200,{item: "banana", type: "fruit"})
        }
    }
    else {
        var plant =  Math.floor(Math.random() * (100)%3);
        switch (plant) {
            case 0: res.send(200,{item: "cucumber", type: "vegetable"})
            case 1: res.send(200,{item: "potatoes", type: "vegetable"})
        }
    }
    return next();
});



server.listen(3000);