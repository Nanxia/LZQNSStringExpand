#LZQNSStringExpand （字符串扩展）

## Example

```objectiveC
- (void)viewDidLoad
{
    [super viewDidLoad];
	
	NSString *originString = @"我是中国人。I am Chinese.";
	
	/** base64 **/
	NSString *encodeBase64Str = [originString sl_encodeToBase64];
	NSString *decodeBase64Str = [encodeBase64Str sl_decodeToBase64];
	
	NSLog(@"======= base64 ======");
	NSLog(@"encodeBase64Str=%@", encodeBase64Str);
	NSLog(@"decodeBase64Str=%@", decodeBase64Str);
	
	/** Email **/
	NSString *emailStr = @"LZQ@qq.cn";
	NSString *noEmailStr = @"LZQ";
	
	NSLog(@"======= Email ======");
	NSLog(@"emailStr is Email: %@", [emailStr sl_isEmail] ? @"YES" : @"NO");
	NSLog(@"noEmailStr is Email: %@", [noEmailStr sl_isEmail] ? @"YES" : @"NO");
	
	/*JSON*/
	NSDictionary *dic = @{@"name": @"chenjm",
						  @"id": @"Programmer",
						  @"Type":@"ios",
						  @"email":@"LZQ@qq.cn"};
	
	NSString *compactJsonStr = [NSString sl_stringWithJsonObject:dic isCompact:YES];
	NSString *noCompactJsonStr = [NSString sl_stringWithJsonObject:dic isCompact:NO];

	NSLog(@"======= JSON ======");
	NSLog(@"compactJsonStr=%@", compactJsonStr);
	NSLog(@"noCompactJsonStr=%@", noCompactJsonStr);
	
	/*MD5*/
	NSString *md5 = [originString sl_MD5];
	NSString *md5Hash = [originString sl_md5Hash];
	
	NSLog(@"======= md5 ======");
	NSLog(@"md5=%@", md5);
	NSLog(@"md5Hash=%@", md5Hash);
	
	/*SHA*/
	NSString *SHA1 = [originString sl_SHA1];
	NSString *SHA256 = [originString sl_SHA256];
	NSString *SHA512 = [originString sl_SHA512];
	
	NSLog(@"======= SHA ======");
	NSLog(@"SHA1=%@", SHA1);
	NSLog(@"SHA256=%@", SHA256);
	NSLog(@"SHA512=%@", SHA512);
	
	/*url*/
	NSString *URLEncode = [originString sl_urlEncode];
	NSString *URLDecode = [originString sl_urlDecode];
    
    NSString *url = @"%e4%ba%8c%e5%8d%81%e5%9b%9b%e8%8a%82%e6%b0%94+%e4%bb%8a%e6%97%a5%e7%ab%8b%e5%86%ac";
    NSString *URLDecodeForPlusConvertToBlank = [url sl_urlDecodeForPlusConvertToBlank];
	
	NSLog(@"======= URLCode ======");
	NSLog(@"URLEncode=%@", URLEncode);
	NSLog(@"URLDecode=%@", URLDecode);
    NSLog(@"URLDecodeForPlusConvertToBlank=%@", URLDecodeForPlusConvertToBlank);
}
```

打印结果：

```
2016-11-07 16:17:30.067 SLNSStringExpand_Example[14719:153403] ======= base64 ======
2016-11-07 16:17:30.068 SLNSStringExpand_Example[14719:153403] encodeBase64Str=5oiR5piv5Lit5Zu95Lq644CCSSBhbSBDaGluZXNlLg==
2016-11-07 16:17:30.068 SLNSStringExpand_Example[14719:153403] decodeBase64Str=我是中国人。I am Chinese.
2016-11-07 16:17:30.069 SLNSStringExpand_Example[14719:153403] ======= Email ======
2016-11-07 16:17:30.083 SLNSStringExpand_Example[14719:153403] emailStr is Email: YES
2016-11-07 16:17:30.084 SLNSStringExpand_Example[14719:153403] noEmailStr is Email: NO
2016-11-07 16:17:30.084 SLNSStringExpand_Example[14719:153403] ======= JSON ======
2016-11-07 16:17:30.085 SLNSStringExpand_Example[14719:153403] compactJsonStr={"email":"LZQ@qq.cn","id":"Programmer","Type":"ios","name":"LZQ"}
2016-11-07 16:17:30.085 SLNSStringExpand_Example[14719:153403] noCompactJsonStr={
  "email" : "LZQ@qq.cn",
  "id" : "Programmer",
  "Type" : "ios",
  "name" : "LZQ"
}
2016-11-07 16:17:30.086 SLNSStringExpand_Example[14719:153403] ======= md5 ======
2016-11-07 16:17:30.086 SLNSStringExpand_Example[14719:153403] md5=f00305c567fa89d9f3c2962f973b862f
2016-11-07 16:17:30.087 SLNSStringExpand_Example[14719:153403] md5Hash=f00305c567fa89d9f3c2962f973b862f
2016-11-07 16:17:30.088 SLNSStringExpand_Example[14719:153403] ======= SHA ======
2016-11-07 16:17:30.088 SLNSStringExpand_Example[14719:153403] SHA1=dc4c69964a0e5a4808f45fcb4c6f91d2e00fa822
2016-11-07 16:17:30.089 SLNSStringExpand_Example[14719:153403] SHA256=7b32eef6a6c86d54b4fcf1f5b2dc8232b10aa203bd8f872c171f6ef62dc85d0a
2016-11-07 16:17:30.090 SLNSStringExpand_Example[14719:153403] SHA512=febd7771b38722b2f05e65e5df0d1f71d07c0d15e47848106e354c3d909dc3b1a22d636848a41de1627eda150787232a184de8a6c11468851451b8936207208f
2016-11-07 16:17:30.091 SLNSStringExpand_Example[14719:153403] ======= URLCode ======
2016-11-07 16:17:30.092 SLNSStringExpand_Example[14719:153403] URLEncode=%E6%88%91%E6%98%AF%E4%B8%AD%E5%9B%BD%E4%BA%BA%E3%80%82I%20am%20Chinese.
2016-11-07 16:17:30.093 SLNSStringExpand_Example[14719:153403] URLDecode=我是中国人。I am Chinese.
2016-11-07 16:17:30.094 SLNSStringExpand_Example[14719:153403] URLDecodeForPlusConvertToBlank=二十四节气 今日立冬
```

## Installation

```ruby
pod "LZQNSStringExpand"
```

## Author

LZQ

## License

LZQNSStringExpand is available under the MIT license. See the LICENSE file for more info.


