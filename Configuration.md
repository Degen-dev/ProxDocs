# Basic Configuration
Different proxies have different ways to configure them. This will go over how to configure [Ultraviolet](https://github.com/titaniumnetwork-dev/Ultraviolet).
## Ultraviolet
Ultraviolet has its configuration in a file called `uv.config.js`. In this case of Degeneracy, this file can be found in `public/uv/uv.config.js`. See the default configuration below:
```js
self.__uv$config = {
    prefix: '/service/',
    bare: '/bare/',
    encodeUrl: Ultraviolet.codec.xor.encode,
    decodeUrl: Ultraviolet.codec.xor.decode,
    handler: '/uv/uv.handler.js',
    bundle: '/uv/uv.bundle.js',
    config: '/uv/uv.config.js',
    sw: '/uv/uv.sw.js',
};
```
The meaning for each configurable option can be found below:
| Configuration | Options and Explanation |
| ------------- | ----------------------- |
| Prefix | The prefix is the prefix that you want users to see. Ex: `https://example.com/service.` The default prefix is `service`. |
| Bare | Bare Servers can run on directories. For example, if the directory was /bare/ then the bare origin would look like `http://example.org/bare/`. The bare origin is passed to clients. |
| encodeUrl| EncodeUrl is how you want the URL a proxy site's visitors has to be encoded. Options include `Ultraviolet.codec.base64.encode`, `Ultraviolet.codec.plain.encode`, or `Ultraviolet.codec.xor.encode`. It is recommended that you use `xor` or `base64` as it hides the queries your visitors are searching and visiting.
| decodeURL | DecodeUrl is how you want the url to be decoded. It is recommended you keep it the same as `encodeUrl`. |
| Handler | Handler is the path to the UV handler. The default name and path to this file is `/uv/uv.handler.js`. |
| Bundle | Bundle is the path to the UV bundle file. The default name and path to this file is `uv/uv.bundle.js`. |
| Config | Config is the path to the UV config file. The default name and path to this file is `uv/uv.bundle.js`. |
| SW | SW is the path to the UV Service Worker file. The default name and path to this file is `uv/uv.sw.js`. |

## Authors
- [Degen-dev (Degenerate)](https://github.com/Degen-dev)