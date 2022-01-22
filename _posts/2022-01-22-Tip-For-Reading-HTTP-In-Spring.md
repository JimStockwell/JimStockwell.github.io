When attempting to read an HTTP message in Spring,
as through TestRestTemplate::exchange,
an exception will be thrown trying to deserializing the payload
if the target class does not implement a no-parameter constructor.
