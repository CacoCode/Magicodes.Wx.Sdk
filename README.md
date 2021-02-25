- # Magicodes.Wx.Sdk


## ����
����������ʹ�õ�΢��Sdk���������ں�Sdk��С����Sdk����ҵ΢��Sdk�ȣ��Լ�Abp VNext���ɡ�

[![Build Status](https://dev.azure.com/xinlaiopencode/Magicodes.Wx.Sdk/_apis/build/status/xin-lai.Magicodes.Wx.Sdk?branchName=main)](https://dev.azure.com/xinlaiopencode/Magicodes.Wx.Sdk/_build/latest?definitionId=15&branchName=main)

| **����** |      **Nuget**      |
|----------|:-------------:|
| **Magicodes.Wx.PublicAccount.Sdk** | **[![NuGet](https://buildstats.info/nuget/Magicodes.Wx.PublicAccount.Sdk)](https://www.nuget.org/packages/Magicodes.Wx.PublicAccount.Sdk)** |
| **Magicodes.Wx.PublicAccount.Sdk.AspNet** | **[![NuGet](https://buildstats.info/nuget/Magicodes.Wx.PublicAccount.Sdk.AspNet)](https://www.nuget.org/packages/Magicodes.Wx.PublicAccount.Sdk.AspNet)** |
| **Magicodes.Wx.PublicAccount.Sdk.Abp** | **[![NuGet](https://buildstats.info/nuget/Magicodes.Wx.PublicAccount.Sdk.Abp)](https://www.nuget.org/packages/Magicodes.Wx.PublicAccount.Sdk.Abp)** |

## RoadMap

### ���ں�

- [x] ȫ��

  - [x] �ӿڽ�����ࣨ`ApiResultBase`��

    - [x] ȫ�ַ����루`ReturnCodes`��
    - [x] �Ƿ�ɹ����أ�`IsSuccess`��
    - [x] ��ȡ�쳣�Ѻ���ʾ��Ϣ��`GetFriendlyMessage`��

  - [x] Access Token��ȡ��`ITokenApi`��

  - [x] Token��������`ITokenManager`��

  - [x] Access Token API����ɸѡ����`AccessTokenApiFilter`��

    - [x] IWxApiBase
    - [x] IWxApiWithAccessTokenFilter������`AccessTokenApiFilter`��

  - [x] �������ļ���ȡ���ں�����

    ```json
      "Wx": {
        "PublicAccount": {
          "AppId": "",
          "AppSecret": ""
        }
      }
    ```

  - [x] ����ע�루`WxFuncs`��

    - [x] GetWeChatOptions����ȡ���ں����á�
    - [x] GetAccessTokenByAppId������AppId��ȡAccess Token��
    - [x] CacheAccessToken������Access Token��

  - [x] �쳣��`WxSdkException`��

  - [x] Abp Vnext���ɣ�`Magicodes.Wx.PublicAccount.Sdk.Abp`��

    - [x] WxPublicAccountSdkModule��Ĭ����ʵ��IDistributedCache��

  - [x] Magicodes.Wx.PublicAccount.Sdk.AspNetģ��

    - [x] �¼���Ϣ��������`WxEventController`��
    - [x] �������¼���Ϣ��������`IWxEventsHandler`��
    - [x] ���ں���ҳ�������ࣨ`WxPublicAccountControllerBase`��
    - [x] ���ں���Ȩɸѡ����`WxPublicAccountOAuthFilter`��

- [ ] ������Ϣ����

  - [x] �������¼���Ϣ

    - [x] �������¼���Ϣ���ý����Լ���֤
    - [x] �¼�����
      - [x] ��ע�¼���`FromSubscribeEvent`
      - [x] ȡ����ע�¼���`FromUnsubscribeEvent`
      - [x] ɨ���¼���`FromScanEvent`
      - [x] ����λ��ѡ�����¼���`FromLocationEvent`
      - [x] ����¼���`FromClickEvent`
      - [x] ����˵�������ת�¼���`FromViewEvent`
      - [x] ģ����Ϣ��������¼���`FromTemplateSendJobFinishEvent`
      - [x] ����˵���תС�����¼���`FromViewMiniprogramEvent`
    - [x] ������Ϣ
      - [x] �ı���Ϣ��`FromTextMessage`
      - [x] ͼƬ��Ϣ��`FromImageMessage`
      - [x] ������Ϣ��`FromVoiceMessage`
      - [x] ��Ƶ��Ϣ��`FromVideoMessage`
      - [x] С��Ƶ��Ϣ��`FromShortVideoMessage`
      - [x] ����λ����Ϣ��`FromLocationMessage`
      - [x] ������Ϣ��`FromLinkMessage`
    - [x] ������Ϣ�ظ�
      - [x] �ظ��ı���Ϣ��`ToTextMessage`
      - [x] �ظ�ͼƬ��Ϣ��`ToImageMessage`
      - [x] �ظ�������Ϣ��`ToVoiceMessage`
      - [x] �ظ���Ƶ��Ϣ��`ToVideoMessage`
      - [x] �ظ�������Ϣ��`ToMusicMessage`
      - [x] �ظ�ͼ����Ϣ��`ToNewsMessage`
      - [x] �ظ�����Ϣ�����ظ�����`ToNullMessage`

  - [ ] Ⱥ���ӿ�

  - [ ] api���ô�����������

  - [ ] ��ȡ���ںŵ�ǰʹ�õ��Զ��ظ�����

  - [ ] ���ں�һ���Զ�����Ϣ

  - [ ] ģ����Ϣ��`ITemplateApi`��

    - [ ] [1 ����������ҵ](https://developers.weixin.qq.com/doc/offiaccount/Message_Management/Template_Message_Interface.html#0)

    - [ ] [2 ��ȡ���õ���ҵ��Ϣ](https://developers.weixin.qq.com/doc/offiaccount/Message_Management/Template_Message_Interface.html#1)

      [3 ���ģ��ID](https://developers.weixin.qq.com/doc/offiaccount/Message_Management/Template_Message_Interface.html#2)

      [4 ��ȡģ���б�](https://developers.weixin.qq.com/doc/offiaccount/Message_Management/Template_Message_Interface.html#3)

      [5 ɾ��ģ��](https://developers.weixin.qq.com/doc/offiaccount/Message_Management/Template_Message_Interface.html#4)

    - [x] [6 ����ģ����Ϣ](https://developers.weixin.qq.com/doc/offiaccount/Message_Management/Template_Message_Interface.html#5)��`SendAsync`��

      [7 �¼�����](https://developers.weixin.qq.com/doc/offiaccount/Message_Management/Template_Message_Interface.html#6)

- [ ] �Զ���˵���`IMenuApi`��

  - [x] �����ӿڣ�`CreateAsync`��
  - [x] ��ѯ�ӿڣ�`GetAsync`��
  - [x] ɾ���ӿڣ�`DeleteAsync`��
  - [ ] ���Ի��˵��ӿ�
  - [ ] ��ȡ�Զ���˵�����

- [ ] ����֪ͨ

  - [ ] ѡ��ģ��
  - [ ] ɾ��ģ��
  - [ ] ��ȡ���ں���Ŀ
  - [ ] ��ȡģ���еĹؼ���
  - [ ] ��ȡ������Ŀ�Ĺ���ģ��
  - [ ] ��ȡ˽��ģ���б�
  - [ ] ���Ͷ���֪ͨ

- [ ] �ͷ���Ϣ

  - [ ] �ͷ�����`IKfAccountApi`��
    - [ ] ��ȡ�ͷ�������Ϣ
    - [x] ��ӿͷ��˺ţ�`AddAsync`��
    - [ ] ����󶨿ͷ��˺�
    - [x] ���ÿͷ���Ϣ��`UpdateAsync`��
    - [ ] �ϴ��ͷ�ͷ��
    - [x] ɾ���ͷ��˺ţ�`DelAsync`��

- [x] ΢����ҳ����

  - [x] ��ҳ��Ȩ
    - [x] ��ȡ��Ȩ���ӣ�`WxHelper >> GetAuthorizeUrl`��
    - [x] ͨ��code��ȡ��ҳ��Ȩaccess_token��`IOauth2Api >> GetAccessTokenAsync`)
    - [x] ˢ��access_token��`IOauth2Api >> RefreshTokenAsync`)
    - [x] ��ȡ�û���Ϣ��`ISnsApi >> GetUserInfoAsync`��
    - [x] ������Ȩƾ֤��access_token���Ƿ���Ч��`ISnsApi >> AuthAsync`��

- [ ] �Ի�����

- [ ] �زĹ���

- [ ] ͼ����Ϣ���Թ���

- [ ] �û�����

- [ ] �˺Ź���

- [ ] ����ͳ��

- [ ] ΢�ſ�ȯ

- [ ] ΢���ŵ�

- [ ] ΢��С��

- [ ] ���ܽӿ�

- [ ] һ��һ��

- [ ] ΢�ŷ�Ʊ

- [ ] ΢�ŷ�˰�ɷ�

### С����

- [ ] ��¼
- [ ] �û���Ϣ
- [ ] ...

## ��������

��Sdk���ַǳ��򵥣��ο��̳�������ʾ��

### 1����װ��

```powershell
Install-Package Magicodes.Wx.PublicAccount.Sdk.AspNet
```

�Ƽ�ʹ�ô˰������ʹ��`Magicodes.Wx.PublicAccount.Sdk`�����и�����Զ������á�

### 2����������

- **�����ļ�����**

���ںŵĲο�����������ʾ������`appsettings.json`�ļ��н������ã�

```json
  "Wx": {
    "PublicAccount": {
      "AppId": "",
      "AppSecret": ""
    }
```

- **ͨ����������**

  �ο�����������ʾ��

  ```csharp
          app.UseMagicodesWeChatSdk(setup =>
          {
              setup.GetWeChatOptions = () =>
              {
                  //����
                  return new WxPublicAccountOption()
                  {
                      AppId = "",
                      AppSecret = ""
                  };
              };
          });
  ```

### 3������Sdk

�ο�����������ʾ��

```csharp
        public void ConfigureServices(IServiceCollection services)
        {
            //��ӹ��ں�Sdk����
            services.AddMPublicAccountSdk()
                //ʹ���ڴ滺��
                .AddDistributedMemoryCache();
        }

        public void Configure(IApplicationBuilder app)
        {
            //���ù��ں�Sdk
            app.UseMPublicAccountSdk()
                //ʹ�÷ֲ�ʽ���滺��Access Token
                .UseWxDistributedCacheForAccessToken();
        }
```
### 4������Api

�������ͼ��ˣ�ͨ������ע��ķ�ʽע�����Api�����繹�캯��ע�룺

```csharp
    public HomeController(IMenuApi menuApi)
    {
        _menuApi = menuApi;
    }
```
Ȼ��Ϳ���ʹ���ˣ���������룺

```csharp
        var result = await _menuApi.CreateAsync(new CreateMenuInput()
        {
            Button = new List<MenuButtonBase>()
            {
                new ClickButton()
                {
                    Name = "���ո���",
                    Key = "V1001_TODAY_MUSIC"
                },
                new SubMenuButton()
                {
                    Name = "�˵�",
                    SubButtons = new List<MenuButtonBase>()
                    {
                        new ViewButton()
                        {
                            Name = "����",
                            Url = "http://www.soso.com/"
                        },
                        //�����С�����
                        //new MiniprogramButton()
                        //{
                        //    Name = "wxa",
                        //    Url = "http://mp.weixin.qq.com",
                        //    AppId = "wx286b93c14bbf93aa",
                        //    Pagepath = "pages/lunar/index"
                        //},
                        new ClickButton()
                        {
                            Name = "��һ������",
                            Key = "V1001_GOOD"
                        }
                    }
                }
            }
        }); 
        result.EnsureSuccess();
```
## ΢�ŷ������¼�����Ϣ����ͱ�����Ϣ�ظ�

��δ���΢�ŷ������¼�����Ϣ������������ʾ��

### 1������Sdk

nuget���İ�װ�͹��ںŵ�������������������ֱ�����Sdk���ô��룺

```csharp
    public void ConfigureServices(IServiceCollection services)
    {
        //ע��IWxEventsHandler,���账���Զ����¼���Ϣ,�����ʵ��IWxEventsHandler
        services.AddSingleton<IWxEventsHandler, TestWxEventsHandler>();
        services.AddMPublicAccountSdk()
            .AddDistributedMemoryCache()
            //��ӷ�������Ϣ�¼�������
            .AddServerMessageHandler();
    }

    public void Configure(IApplicationBuilder app)
    {
        //���ù��ں�Sdk
        app.UseMPublicAccountSdk()
            //ʹ�÷ֲ�ʽ���滺��Access Token
            .UseWxDistributedCacheForAccessToken();
    }
```
### 2��ʵ��IWxEventsHandler

�ο�����������ʾ��

```csharp
/// <summary>
/// ���ں��¼���Ϣ�������
/// </summary>
public class TestWxEventsHandler : IWxEventsHandler
{
    /// <summary>
    /// ִ��
    /// </summary>
    /// <param name="fromMessage"></param>
    /// <returns></returns>
    public async Task<ToMessageBase> Execute(IFromMessage fromMessage)
    {
        if (fromMessage is FromTextMessage)
        {
            //���ض�ͼ��
            var toMsg = new ToNewsMessage()
            {
                Articles = new List<ToNewsMessage.ArticleInfo>()
                {
                    new ToNewsMessage.ArticleInfo()
                    {
                        Description = "����������ʹ�õ�΢��Sdk���������ں�Sdk��С����Sdk����ҵ΢��Sdk�ȣ��Լ�Abp VNext���ɡ�",
                        PicUrl = "https://www.xin-lai.com/imgs/xinlai-logo_9d2c29c2794e6a173738bf92b056ab69.png",
                        Title="Magicodes.Wx.Sdk���",
                        Url = "http://xin-lai.com"
                    }
                },
                FromUserName = "Test",
                ToUserName = "Test"
            };
            return await Task.FromResult(toMsg);
        }
        else if (fromMessage is FromSubscribeEvent)
        {
            //�����ı���Ϣ
            return await Task.FromResult(new ToTextMessage()
            {
                Content = "��ӭ��ע!",
            });
        }
        else if (fromMessage is FromTextMessage)
        {
            //�����ı�
            return await Task.FromResult(new ToTextMessage()
            {
                Content = "Test",
            });
        }
        return await Task.FromResult(new ToNullMessage());
    }
}
```

����¼�����Ϣ�Լ���Ϣ�ظ��Ķ��壬������ʾ��

- �¼�����
  - ��ע�¼���`FromSubscribeEvent`
  - ȡ����ע�¼���`FromUnsubscribeEvent`
  - ɨ���¼���`FromScanEvent`
  - ����λ��ѡ�����¼���`FromLocationEvent`
  - ����¼���`FromClickEvent`
  - ����˵�������ת�¼���`FromViewEvent`
  - ģ����Ϣ��������¼���`FromTemplateSendJobFinishEvent`
  - ����˵���תС�����¼���`FromViewMiniprogramEvent`

- ������Ϣ
  - �ı���Ϣ��`FromTextMessage`
  - ͼƬ��Ϣ��`FromImageMessage`
  - ������Ϣ��`FromVoiceMessage`
  - ��Ƶ��Ϣ��`FromVideoMessage`
  - С��Ƶ��Ϣ��`FromShortVideoMessage`
  - ����λ����Ϣ��`FromLocationMessage`
  - ������Ϣ��`FromLinkMessage`

- ������Ϣ�ظ�
  - �ظ��ı���Ϣ��`ToTextMessage`
  - �ظ�ͼƬ��Ϣ��`ToImageMessage`
  - �ظ�������Ϣ��`ToVoiceMessage`
  - �ظ���Ƶ��Ϣ��`ToVideoMessage`
  - �ظ�������Ϣ��`ToMusicMessage`
  - �ظ�ͼ����Ϣ��`ToNewsMessage`
  - �ظ�����Ϣ�����ظ�����`ToNullMessage`

## MVC��ҳ��Ȩ

��ASP.NET MVC�����ǿ���ͨ����SDK���ٻ��΢���û���Ϣ���ο�����������ʾ��

```csharp
//ע��̳�WxPublicAccountControllerBase
public class HomeController : WxPublicAccountControllerBase
{
    private readonly ILogger<HomeController> _logger;

    public HomeController(ILogger<HomeController> logger)
    {
        _logger = logger;
    }
    //������WxPublicAccountOAuthFilter��Action�ڻ�����ڵ�����£����Զ���ת��΢����ҳ��Ȩҳ�������Ȩ
    //OAuthLevel����ΪOpenIdAndUserInfo�����ȡ��˿��Ϣ
    [WxPublicAccountOAuthFilter(OAuthLevel = OAuthLevels.OpenIdAndUserInfo)]
    public async Task<IActionResult> IndexAsync()
    {
        //���ø����������Ļ�ȡ��˿��Ϣ�������÷�����ISnsApi�л�ȡ��˿��ϸ��Ϣ
        var userResult = await GetWeChatUserInfoAsync();
        var model = new UserInfo()
        {
            Headimgurl = userResult.Headimgurl,
            NickName = userResult.NickName,
            Sex = userResult.Sex
        };
        _logger.LogDebug($"NickName:{userResult.NickName}");
        return View(model);
    }
}
```
## Abp VNext����

Magicodes.Wx.PublicAccount.SdkĬ���ṩ��Abp VNextģ�飬��ز���������ʾ��

### 1����װMagicodes.Wx.PublicAccount.Sdk.Abp

```powershell
Install-Package Magicodes.Wx.PublicAccount.Sdk.Abp
```

### 2�����ģ������

```csharp
[DependsOn(
    typeof(WxPublicAccountSdkModule)
)]
```
���账��������¼���Ϣ������ע��IWxEventsHandler��

```csharp
context.Services.AddSingleton<IWxEventsHandler, WxEventsHandler>();
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