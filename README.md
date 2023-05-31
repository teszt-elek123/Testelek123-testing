# Testelek123-testing

require_once("../common/php/environment.php");
$db = new Database("test");
$result = $db ->execute("SELECT * FROM car");
Util::setResponse($result);
