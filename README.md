# A mini example for C/C++ http/websocket server

## Build example

```
$ git clone https://github.com/hguo/mini-cxx-http-example
$ cd mini-cxx-http-example
$ cd build
$ cmake -DBOOST_ROOT=${your_boost_installation} -DCMAKE_INSTALL_PREFIX=${prefix}
$ make && make install
```

The header, library, and executable will be installed to `${prefix}`. 

## Test example

1. Create a file /tmp/test, and add arbitrary contents, e.g. 

> This is a test.

2. Run the example

```
$ cd ${prefix}
$ ./bin/test_zserver 9091
```

where 9091 is the port number.

3. Open a web browser and visit http://localhost:9091/get?key, you will see the contents in /tmp/test.

Please read main.c for more details.

## C/C++ API

The API is in zserver.h.  

### zserver_start

Call `zserver_start(int port)` to start a http server that binds the port.  The function will return immediately after creating a thread that runs the http server.  

### zserver_stop

Call `zserver_stop()` to stop the http server.

### zserver_commit_file

Call `zserver_commit_file(const char *key, const char *filename)` to add a filename into the key-value store.  

## HTTP Client

You can retrieve the content of the file using the url `http://your_server_address:port/get?your_key_name`