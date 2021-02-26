# ��ο��ٱ�дһ��΢��Api��


## ����
[Magicodes.Wx.Sdk](https://github.com/xin-lai/Magicodes.Wx.Sdk)�����ڴ�������������ʹ�õ�΢��Sdk���𲽰������ں�Sdk��С����Sdk����ҵ΢��Sdk�ȣ��Լ�Abp VNext���ɡ�

��ƪ�������ڽ��������[Magicodes.Wx.Sdk](https://github.com/xin-lai/Magicodes.Wx.Sdk)���й��ס�

## WebApiClientCore

[Magicodes.Wx.Sdk](https://github.com/xin-lai/Magicodes.Wx.Sdk)֮���ܴ����������NCC�Ŀ�Դ��[WebApiClientCore](https://github.com/dotnetcore/WebApiClient)��

��Դ���ַ��https://github.com/dotnetcore/WebApiClient

## ���ٿ�ʼ

���������ԡ��ͷ���Ϣ������ӿͷ��˺š�Ϊ�����н��⣬�ٷ��ӿ��ĵ���ַΪ��https://developers.weixin.qq.com/doc/offiaccount/Customer_Service/Customer_Service_Management.html#2��

![��ӿͷ��˺�](../res/image-20210226095153459.png)

���岽�����£�

### 1����ӽӿ�IKfAccountApi

�ο�����������ʾ��

```csharp
/// <summary>
/// �ͷ�����
/// </summary>
[HttpHost("https://api.weixin.qq.com/customservice/kfaccount")]
public interface IKfAccountApi : IWxApiWithAccessTokenFilter
{
    /// <summary>
    /// ��ӿͷ��˺�
    /// </summary>
    /// <param name="input"></param>
    /// <returns></returns>
    [HttpPost("add")]
    Task<ApiResultBase> AddAsync(AddOrUpdateKfAccountInput input);

    /// <summary>
    /// ���ÿͷ���Ϣ
    /// </summary>
    /// <param name="input"></param>
    /// <returns></returns>
    [HttpPost("update")]
    Task<ApiResultBase> UpdateAsync(AddOrUpdateKfAccountInput input);

    /// <summary>
    /// ɾ���ͷ��˺�
    /// </summary>
    /// <param name="input"></param>
    /// <returns></returns>
    [HttpPost("del")]
    Task<ApiResultBase> DelAsync(DelKfAccountInput input);
}
```
������������ʾ���м���ע�����

1. ��Ҫ����ӿ�

2. �̳���IWxApiWithAccessTokenFilter�ӿڽ��Զ��ڽӿ���������AccessTokenApiFilterɸѡ���������Զ����ڽӿ�����ʱ����access_token��

3. HttpHost���ڶ���ӿڸ���ַ

4. HttpPost�������ýӿ����󷽷������������У�

   | ��������                | ��������                     | ��ע                     |
   | ----------------------- | ---------------------------- | ------------------------ |
   | HttpHostAttribute       | �������http���������������� | ���ȼ���Options���õ�    |
   | HttpGetAttribute        | ����Get���󷽷���·��        | ֧��null�����Ի����·�� |
   | HttpPostAttribute       | ����Post���󷽷���·��       | ֧��null�����Ի����·�� |
   | HttpPutAttribute        | ����Put���󷽷���·��        | ֧��null�����Ի����·�� |
   | HttpDeleteAttribute     | ����Delete���󷽷���·��     | ֧��null�����Ի����·�� |
   | *HeaderAttribute*       | ��������ͷ                   | ����ֵ                   |
   | *TimeoutAttribute*      | ������ʱʱ��                 | ����ֵ                   |
   | *FormFieldAttribute*    | ����Form���ֶ���ֵ         | ��������ֵ               |
   | *FormDataTextAttribute* | ����FormData���ֶ���ֵ     | ��������ֵ               |

### 2�����Dto

��һ���ǷǱ�Ҫ�ģ���Ҫ�������ľ������ݺ�Ҫ����ӿͷ��ӿڵ������������ο����£�

```csharp
    public class AddOrUpdateKfAccountInput
    {
        /// <summary>
        /// �����ͷ��ʺţ���ʽΪ���ʺ�ǰ׺@���ں�΢�źţ��ʺ�ǰ׺���10���ַ���������Ӣ�ġ������ַ������»��ߣ���׺Ϊ���ں�΢�źţ����Ȳ�����30���ַ�
        /// </summary>
        [JsonProperty("kf_account")]
        [StringLength(30, MinimumLength = 3)]
        [Required]
        public string Account { get; set; }

        /// <summary>
        /// �ͷ��ǳƣ��16����
        /// </summary>
        [JsonProperty("nickname")]
        [StringLength(16, MinimumLength = 1)]
        public string Nickname { get; set; }
    }
```
### 3�����ApiResultBase

����з�װ��Ĭ�ϵķ��ؽ�����࣬���û����������ķ������ݣ����践��`ApiResultBase`���ɡ�����ж���ķ�Χ���ݣ�����Ҫ��������̳���`ApiResultBase`���ڿ��ܵ�����£��п�����Ҫ��д���ַ��������������룺

```csharp
public class TokenApiResult : ApiResultBase
{
    /// <summary>
    ///     ��ȡ����ƾ֤
    /// </summary>
    [JsonProperty("access_token")]
    public string AccessToken { get; set; }

    /// <summary>
    ///     ƾ֤��Чʱ�䣬��λ����
    /// </summary>
    [JsonProperty("expires_in")]
    internal int Expires { get; set; }

    /// <summary>
    ///     ƾ֤����ʱ��
    /// </summary>
    public DateTime ExpiresTime { get; set; }
}
```
���ˣ�һ���ӿھͱ�д����ˡ�ֻ��Ҫ����interface��Dto�Ϳ����ˡ��ǲ��Ƿǳ��򵥣�

### 4����Ԫ���Ա�д

```csharp
/// <summary>
/// ģ����Ϣ��Ԫ����
/// </summary>
public class TemplateApiTest : TestBase, IClassFixture<TestWebApplicationFactory>
{
    private readonly ITemplateApi templateApi;
    public TemplateApiTest(TestWebApplicationFactory webApplicationFactory, ITestOutputHelper output) : base(webApplicationFactory, output)
    {
        //ͨ�������GetRequiredService��ȡ��Api
        templateApi = GetRequiredService<ITemplateApi>();
    }

    /// <summary>
    /// ģ����Ϣ���Ͳ���
    /// </summary>
    /// <returns></returns>
    [Fact]
    public async Task SendAsync_Test()
    {
        var result = await templateApi.SendAsync(new SendTemplateMessageInput()
        {
            To = "oXELNwzZgamuLS0JrJhVgdelzKyw",
            TemplateId = "riid7aad8OKRQD9Ey6dclWBBkrqZSFDhlpKh0_spGLA",
            Data = new System.Collections.Generic.Dictionary<string, TemplateDataItem>()
            {
                {"first",new TemplateDataItem("����") },
                {"keyword1",new TemplateDataItem("ѩ��") },
                {"keyword2",new TemplateDataItem("2021.2.5") },
                {"remark",new TemplateDataItem("��ע") },
            }
        });
        //�ж�Api�Ƿ���óɹ���δ�ɹ����׳��쳣WxSdkException
        result.EnsureSuccess();
    }
}
```
����ο���

https://github.com/xin-lai/Magicodes.Wx.Sdk/pull/1/commits/85263ed9a807581f7315a90fe6e00c51c994d386

## ����

### IWxApiWithAccessTokenFilter�ӿ�

�ο����룺

```csharp
/// <summary>
/// 
/// </summary>
[JsonNetReturn(EnsureMatchAcceptContentType = false)]
[AccessTokenApiFilter]
//[LoggingFilter]
public interface IWxApiWithAccessTokenFilter
{
}
```
### AccessTokenApiFilterɸѡ��

�ο����룺

```csharp
public class AccessTokenApiFilter : ApiFilterAttribute
{
    public override async Task OnRequestAsync(ApiRequestContext context)
    {
        ITokenManager tokenManager = context.HttpContext.ServiceProvider.GetRequiredService<ITokenManager>();
        string accessToken = await tokenManager.GetAccessTokenAsync();
        context.HttpContext.RequestMessage.AddUrlQuery("access_token", accessToken);
    }

    public override Task OnResponseAsync(ApiResponseContext context)
    {
        return Task.CompletedTask;
    }
}
```
### ����ApiResultBase

```csharp
/// <summary>
///     API������
///     {"errcode":40164,"errmsg":"invalid ip 218.76.8.29 ipv6 ::ffff:218.76.8.29, not in whitelist rid: 60122c35-705c3134-51b45a3d"}
/// </summary>
public class ApiResultBase
{
    /// <summary>
    ///     ������
    /// </summary>
    [JsonProperty("errcode")]
    public virtual ReturnCodes ReturnCode { get; set; }

    /// <summary>
    ///     ������Ϣ
    /// </summary>
    [JsonProperty("errmsg")]
    public virtual string Message { get; set; }

    /// <summary>
    ///     �Ƿ�Ϊ�ɹ�����
    /// </summary>
    /// <returns></returns>
    public virtual bool IsSuccess()
    {
        return ReturnCode == ReturnCodes.����ɹ�;
    }

    /// <summary>
    ///     ��ȡ�Ѻ���ʾ
    /// </summary>
    /// <returns></returns>
    public virtual string GetFriendlyMessage()
    {
        return ReturnCode.ToString();
    }
}
```
## ��ϵ����

### ���ĺ�
��ע��**����ļ���**�����ĺſ��Ի���������¡��̡̳��ĵ������Ҽ���΢����̬Ⱥ��
![](https://docs.xin-lai.com/medias/wechat.jpg "����ļ���")

### QQȺ

- **��̽���Ⱥ<85318032>**�����ڲ��������ߣ�Ϊ�˱���ɧ�ţ�������һ���ż���


#### �ĵ�����&�ٷ�����

- **�ĵ�������<https://docs.xin-lai.com/>**
- **���ͣ�<http://www.cnblogs.com/codelove/>**

#### ������Դ��

- **<https://github.com/xin-lai>**
- **<https://gitee.com/magicodes>**