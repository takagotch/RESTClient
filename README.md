### RESTClient
---

https://github.com/rest-client/rest-client


```sh
response = RestClient.get 'http://example.com/resource'
response.code
response.cookies
response.headers
response.body

RestClietn.get 'http://example.com/nonexistent'
begin
  RestClient.get 'http://example.com/nonexistent'
rescue RestClient::exceptionWithResponse => e
  e.response
end

RestClient.get 'http://localhost:12345'

r = RestClient.get('http://httpbin.org/redirect/2')
r.histroy
r.request.url
r.histroy.map {|x| x.request.url}

RestClient::Request.execute(method: :get, url: 'http://httpbin.org/redirect/1')
RestClient;:Request.execute(method: :get, url: 'http://httpbin.org/redirect/1', max_redirects: 0)

RestClient::Request.execute()









```

```ruby
require 'rest-client'
RestClient.get(url, headers={})
RestClient.post(url, payload, headers={})

require 'rest-client'
RestClient.get 'http://example.com/resource'
RestClient.get 'http://example.com/resource', {params: {id: 50, 'foo' => 'bar'}}
RestClient.get 'http://user:password@example.com/private/resource', {accept: :json}
RestClient.post 'http://example.com/resource', {param1: 'one', nested: {param2: 'two'}}
RestClient.post "http://example.com/resource", {'x' => 1}.to_json, {content_type: :json, accept: :json}
RestClient.delete 'http://example.com/resource'

RestClient.post( url,
  {
    :transfer => {
      :path => '/goo/bar',
      :owner => 'that_guy',
      :group => 'those_guys'
    },
    :upload => {
      :file => File.new(path, 'rb')
    }
  })
  
RestClient::Request.execute(method: :get, url: 'http://example.com/resource',
                            timeout: 10)
RestClient::Request.execute(method: :get, url: 'http://example.com/resource',
                            ssl_ca_file: 'myca.pem',
                            ssl_ciphers: 'AESGCM:!aNULL')

RestClient::Request.execute(method: :delete, url: 'http://example.com/resource',
                            payload: 'goo', headers: {myheader: 'bar'})
RestClient::Request.execute(method: :get, url: 'http://example.com/resource',
                            timeout: 10, headers: {params: {foo: 'bar'}})

RestClient.post '/data', :myfile => File.new("/path/to/image.jpg", 'rb')
RestClient.post '/data', {:foo => 'bar', :multipart => true}

resource = RestClient::Resource.new 'http://example.com/resource'
resource.get
private_resource = RestClient::Resource.new 'https://example.com/private/resource', 'user', 'pass'
private_resource.put File.read('pic.jpg'), :content_type => 'image/jpg'

site = RestClient::Resource.new('http://example.com')
site['posts/1/comments'].post '', :content_type => 'text/plain'


```

```

```
