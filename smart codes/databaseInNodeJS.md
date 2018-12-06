## Database loop in sync
```
function dataBaseLoop() {
    var returnMsg = '';
    db.serialize(function() {
        db.run('BEGIN TRANSACTION;');
        var length = 10;
        for(var i = 0; i < length; i++) {
            var sql; //sentence
            var k = 0;
            db.run(sql, function(err, rows) {
                if(!err) {
                    k++;
                    //当所有的回调都执行完成时，返回错误
                    if(k == length) {
                        if(returnMsg) {
                            console.log('errMessage:',returnMsg);
                        } else {
                            console.log('成功！');
                        };
                        
                    };
                } else {
                    returnMsg += '[数据：' + data.vals[k] + '新增失败，' + err + ']';
                    k++;
                    if(k == length) {     
                        if(returnMsg) {
                            console.log('errMessage:',returnMsg);
                        } else {
                            console.log('成功！');
                        };
                    };
                };    
            });
        };       
        db.run('COMMIT TRANSACTION;');
    });  
};
```