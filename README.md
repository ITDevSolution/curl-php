# curl-php
clase sencilla para utilizar fácilmente la librería curl.

### uso simplificado
```sh
	$conect = new cURL();
	$html = $curl->send("URL"); // GET
	
	$html = $curl->send("URL", $array); //POST  => array( "name"=>"value" )
```

### opciones
```sh
	// POST
	$curl = new cURL();
	$curl->setReferer( "URL" ); // cambia url de referencia
	$curl->setHttpHeader( $array ); // cambia header ejm: array('Content-Type'=>'application/json;charset=UTF-8');
	$curl->setCustomRequest( $string ); // cambia metodo ( GET | HEAD | POST | CONNECT | DELETE | UPDATE | .... )
```

### send POST
```sh
	$curl = new cURL();
	$curl->setPost($array); // cambia campo POST ejm: array("name"=>"value","name2"=>"value2")
	$html = $curl->connect( "URL" );
```

### send GET
```sh
	$curl = new cURL();
	$html = $curl->connect( "URL" );
```

### send Binary
```sh
	$curl = new cURL();
	$curl->setBinary( $string ); // cambia campo BINARY
	$response = $curl->connect( "URL" );
```

### Use PROXY
```sh
	$curl = new cURL();
	$curl->useProxy(true);
	$curl->setProxyHost("127.0.0.1");
	$curl->setProxyPort("3128");
	$curl->setProxyType( CURLPROXY_SOCKS5 );
	// auth proxy
	$curl->setProxyUser( "user" );
	$curl->setProxyPass( "pass" );
```
