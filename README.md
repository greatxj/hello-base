# Hellobase

> hello Hbase

## installation

`composer require fatrbaby/hellobase`

## usage

```php
use HelloBase\Connection;

$config = [
    'host' => 'localhost',
    'port' => '9090',
    'persist' => false,
    'debug_handler' => null,
    'send_timeout' => 1000000,
    'recv_timeout' => 1000000,
    'transport' => 'buffered',
    'protocol' => 'binary_accelerated',
];

$connection = new Connection($config);
$connection->connect();

# get tables 
$connection->tables();

# get table instance
$table = $connection->table('tableName');

# put data
$table->put('row-name', ['cf:foo' => 'bar']);

# get row
$table->row('row-name', ['column1', ...]);

# get rows
$table->rows(['row-name1', 'row-name2', ...], ['column1', ...]);

# increment 
$table->increment('row-name', 'column-name', int amount)

# scan
foreach($table->scan(<startRow>, <stopRow>, <['column1', ...]>, <['condition1', ...]>) as $row => $columns) {
    // do something
}

```

## todo

more features

