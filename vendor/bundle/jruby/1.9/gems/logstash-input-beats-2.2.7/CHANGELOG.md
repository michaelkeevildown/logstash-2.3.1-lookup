# 2.2.7
  - More robust test when using a random port #60
  - Fix LSF integration tests #52
# 2.2.6
  - Do not use the identity map if we don't explicitly use the `multiline` codec
# 2.2.5
  - Fix failing tests introduce by the `ssl_key_passphrase` changes.
  - Added an integration test for the `ssl_key_passphrase`
  - Add an optional parameter for `auto_flush`
# 2.2.4
  - Fix bug where using `ssl_key_passphrase` wouldn't work 
# 2.2.2
  - Depend on logstash-core-plugin-api instead of logstash-core, removing the need to mass update plugins on major releases of logstash
# 2.2.1
  - New dependency requirements for logstash-core for the 5.0 release
# 2.2.0
  - The server can now do client side verification by providing a list of certificate authorities and configuring the `ssl_verify_mode`,
    the server can use `peer`, if the client send a certificate it will be validated. Using `force_peer` will make sure the client provide a certificate
    and it will be validated with the know CA.  #8
# 2.1.4
  - Change the `logger#warn` for `logger.debug` when a peer get disconnected, keep alive check from proxy can generate a lot of logs  #46
# 2.1.3
  - Make sure we stop all the threads after running the tests #48
# 2.1.2
  - Catch the `java.lang.InterruptedException` in the events broker
  - Give a bit more time to the Thread to be started in the test #42
# 2.1.1
  - Release a new version of the gem that doesn't included any other gems, 2.1.0 is yanked from rubygems 
# 2.1.0
  - Refactor of the code to make it easier to unit test
  - Fix a conncurrency error on high load on the SizeQueue #37
  - Drop the internal SizeQueue to rely on Java Synchronous Queue
  - Remove the majority of the nested blocks
  - Move the CircuitBreaker inside an internal namespace so it doesn't conflict with the input lumberjack
  - Add more debugging log statement
  - Flush the codec when a disconnect happen
  - Tag/Decorate the event when a shutdown occur.
  - The name of the threads managed by the input beat are now meaningful.
# 2.0.3
  - Reduce the size of the gem by removing vendor jars
# 2.0.2
  - Copy the `beat.hostname` field into the `host` field for better compatibility with the other Logstash plugins #28
  - Correctly merge multiple line with the multiline codec ref: #24
# 2.0.0
  - Add support for stream identity, the ID will be generated from beat.id+resource_id or beat.name + beat.source if not present #22 #13
    The identity allow the multiline codec to correctly merge string from multiples files.
# 0.9.6
  - Fix an issue with rogue events created by buffered codecs #19
# 0.9.5
  - Set concurrent-ruby to 0.9.1 see https://github.com/elastic/logstash/issues/4141
# 0.9.4
  - Correctly decorate the event with the `add_field` and `tags` option from the config #12
# 0.9.3
  - Connection#run should rescue `Broken Pipe Error` #5
  - Fix a `SystemCallErr` issue on windows when shutting down the server #9

# 0.9.2
  - fix an issue with the incorrectly calculated ack when the window_size was smaller than the ACK_RATIO see  https://github.com/logstash-plugins/logstash-input-beats/issues/3

# 0.9.1
  - Move the ruby-lumberjack library into the plugin

# 0.9
  - Created from `logstash-input-lumberjack` version 2.0.2 https://github.com/logstash-plugins/logstash-input-lumberjack
  - Use SSL off by default
