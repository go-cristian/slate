# Session

```java

//register your token provider class
pager.tokenProvider(new TokenProvider());

//This class provides a callback to allow SDK know the token and the changes on it.
//The SDK uses an internal thread to allow you call this from a webservice or another source
public class TokenProvider extends SDKTokenProvider {

    @Override
    public String token() {
        String token = ... //My Token Provider 
        return token;
    }
}
```

```kotlin

//register your token provider class
pager.tokenProvider(TokenProvider())

//This class provides a callback to allow SDK know the token and the changes on it.
//The SDK uses an internal thread to allow you call this from a webservice or another source
class TokenProvider: SDKTokenProvider {

    override fun token(service: TokenService): String {
        val token:String = ... //My Token Provider
        return token
    }
}
```

For securing your application the SDK needs to deal with an Auth process this involves the creation of a token provided by your backend, this token will be used by Pager to make sure the user is valid and exists.
