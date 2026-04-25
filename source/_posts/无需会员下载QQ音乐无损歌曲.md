title: 无需会员下载QQ音乐无损歌曲
date: 2018-05-08 0:23:06
categories: 
- skills
tags: 
- Spyder
- QQ music
---

国内现有的几款音乐播放器中，QQ音乐的曲库还是比较全的（非广告）。但很多歌曲是要付费会员才能下载，而且只能通过客户端下载。这几天[@Supreme-Liam](https://blog.lipf.tech)发现了一个爬取QQ音乐的入口，便研究了一下，整理下来。

**请尊重歌曲版权，本文章所述仅用于学习，切莫以此作为商业用途**

<!--more-->

### 搜索你要找的歌曲songmid

获取songmid的url：

`https://c.y.qq.com/soso/fcgi-bin/client_search_cp?&t=0&aggr=1&cr=1&catZhida=1&lossless=0&flag_qc=0&p=1&n=20&w=[歌曲名字]`

e.g.要找赵英俊的“大王叫我来巡山”，在浏览器地址栏中输入

`https://c.y.qq.com/soso/fcgi-bin/client_search_cp?&t=0&aggr=1&cr=1&catZhida=1&lossless=0&flag_qc=0&p=1&n=20&w=大王叫我来巡山`

就会得到一个json文件，包含所有有关“大王叫我来巡山”的歌曲。

```
callback({
	"code": 0,
	"data": {
		"keyword": "大王叫我来巡山",
		"priority": 0,
		"qc": [],
		"semantic": {
			"curnum": 0,
			"curpage": 1,
			"list": [],
			"totalnum": 0
		},
		"song": {
			"curnum": 24,
			"curpage": 1,
			"list": [{
				"albumid": 1838256,
				"albummid": "002ka0Zz44S0Lw",
				"albumname": "2016湖南卫视跨年演唱会",
				"albumname_hilight": "2016湖南卫视跨年演唱会",
				"alertid": 100002,
				"belongCD": 0,
				"cdIdx": 8,
				"chinesesinger": 0,
				"docid": "16660156385534686745",
				"grp": [{
					"albumid": 1282380,
					"albummid": "001vJ2tx3GtoTa",
					"albumname": "“家家好 国家好”2016北京卫视春节联欢晚会",
					"albumname_hilight": "“家家好 国家好”2016北京卫视春节联欢晚会",
					"alertid": 11,
					"belongCD": 0,
					"cdIdx": 2,
					"chinesesinger": 0,
					"docid": "2733224141856809370",
					"format": "qqnormal;common;mp3common;wmacommon;crcommon",
					"interval": 80,
					"isonly": 0,
					"lyric": "",
					"lyric_hilight": "",
					"media_mid": "002Yp3fz3QWD2I",
					"msgid": 0,
					"newStatus": 2,
					"nt": 10003,
					"pay": {
						"payalbum": 0,
						"payalbumprice": 0,
						"paydownload": 0,
						"payinfo": 0,
						"payplay": 0,
						"paytrackmouth": 0,
						"paytrackprice": 0
					},
					"preview": {
						"trybegin": 48470,
						"tryend": 78469,
						"trysize": 481070
					},
					"pubtime": 1454860800,
					"pure": 0,
					"singer": [{
						"id": 160949,
						"mid": "004LcXZN2GYrzw",
						"name": "贾乃亮",
						"name_hilight": "贾乃亮"
					}],
					"size128": 1286302,
					"size320": 0,
					"sizeape": 0,
					"sizeflac": 0,
					"sizeogg": 0,
					"songid": 105577772,
					"songmid": "002Yp3fz3QWD2I",
					"songname": "大王叫我来巡山 (Live)",
					"songname_hilight": "<em>大王叫我来巡山</em> (Live)",
					"songurl": "http://y.qq.com/#type=song&id=105577772",
					"strMediaMid": "002Yp3fz3QWD2I",
					"stream": 10,
					"switch": 1124119,
					"t": 0,
					"tag": 10,
					"type": 0,
					"ver": 0,
					"vid": "y00198rnqkp"
				}],
				"interval": 156,
				"isonly": 1,
				"lyric": "",
				"lyric_hilight": "",
				"media_mid": "002rAFib3Nc7op",
				"msgid": 16,
				"newStatus": 2,
				"nt": 10003,
				"pay": {
					"payalbum": 0,
					"payalbumprice": 0,
					"paydownload": 1,
					"payinfo": 1,
					"payplay": 0,
					"paytrackmouth": 1,
					"paytrackprice": 200
				},
				"preview": {
					"trybegin": 0,
					"tryend": 0,
					"trysize": 0
				},
				"pubtime": 1451577600,
				"pure": 0,
				"singer": [{
					"id": 160949,
					"mid": "004LcXZN2GYrzw",
					"name": "贾乃亮",
					"name_hilight": "贾乃亮"
				}],
				"size128": 2507973,
				"size320": 0,
				"sizeape": 0,
				"sizeflac": 0,
				"sizeogg": 0,
				"songid": 200621134,
				"songmid": "002rAFib3Nc7op",
				"songname": "大王叫我来巡山 (Live)",
				"songname_hilight": "<em>大王叫我来巡山</em> (Live)",
				"strMediaMid": "002rAFib3Nc7op",
				"stream": 6,
				"switch": 17413891,
				"t": 1,
				"tag": 10,
				"type": 0,
				"ver": 0,
				"vid": ""
			},
			{
				"albumid": 1230948,
				"albummid": "000oxFgZ0cV589",
				"albumname": "万万没想到 电影原声带",
				"albumname_hilight": "万万没想到 电影原声带",
				"alertid": 11,
				"belongCD": 0,
				"cdIdx": 2,
				"chinesesinger": 0,
				"docid": "632559568801853934",
				"format": "qqhq;common;mp3common;wmacommon;crcommon",
				"grp": [],
				"interval": 242,
				"isonly": 0,
				"lyric": "《万万没想到》电影插曲",
				"lyric_hilight": "《万万没想到》电影插曲",
				"media_mid": "003qKBfB2nc0RX",
				"msgid": 0,
				"newStatus": 2,
				"nt": 10001,
				"pay": {
					"payalbum": 0,
					"payalbumprice": 0,
					"paydownload": 0,
					"payinfo": 0,
					"payplay": 0,
					"paytrackmouth": 0,
					"paytrackprice": 0
				},
				"preview": {
					"trybegin": 44355,
					"tryend": 74495,
					"trysize": 483159
				},
				"pubtime": 1449504000,
				"pure": 0,
				"singer": [{
					"id": 4289,
					"mid": "002sfdNU1f3nHD",
					"name": "赵英俊",
					"name_hilight": "赵英俊"
				}],
				"size128": 3873445,
				"size320": 9683287,
				"sizeape": 29024681,
				"sizeflac": 29168584,
				"sizeogg": 5903527,
				"songid": 105164089,
				"songmid": "003qKBfB2nc0RX",
				"songname": "大王叫我来巡山",
				"songname_hilight": "<em>大王叫我来巡山</em>",
				"songurl": "http://y.qq.com/#type=song&id=105164089",
				"strMediaMid": "003qKBfB2nc0RX",
				"stream": 8,
				"switch": 3225399,
				"t": 0,
				"tag": 11,
				"type": 0,
				"ver": 0,
				"vid": "z0019u80c82"
			},
...
```
通过歌手名（singer.name）和专辑名（albumname）以及歌曲简介（lyric）基本上可以确定我们要找的这首歌了。随后可以查到这首歌的`songmid = 003qKBfB2nc0RX`

### 获取uin、guid和vkey

通过下面url

`http://c.y.qq.com/base/fcgi-bin/fcg_music_express_mobile3.fcg?g_tk=0&loginUin=[uin]&hostUin=0&format=json&inCharset=utf8&outCharset=utf-8&notice=0&platform=yqq&needNewCode=0&cid=205361747&uin=[uin]&songmid=003qKBfB2nc0RX&filename=C400003a1tne1nSz1Y.m4a&guid=[guid]`

其中只需要修改uin和guid（任意数字），songmid和filename都不用管它，从得到的.cfg中就可以取出key了。

e.g.从这个url：

`http://c.y.qq.com/base/fcgi-bin/fcg_music_express_mobile3.fcg?g_tk=0&loginUin=1&hostUin=0&format=json&inCharset=utf8&outCharset=utf-8&notice=0&platform=yqq&needNewCode=0&cid=205361747&uin=1&songmid=003qKBfB2nc0RX&filename=C400003a1tne1nSz1Y.m4a&guid=2`

得到文件，打开可以看到

```
{
	"code": 0,
	"cid": 205361747,
	"userip": "59.78.171.159",
	"data": {
		"expiration": 80400,
		"items": [{
			"subcode": 0,
			"songmid": "003qKBfB2nc0RX",
			"filename": "C400003a1tne1nSz1Y.m4a",
			"vkey": "5B2AE76142D563F91A8973947CC2BAD89BFA9ECC4ED48928E450A5B01103C5C2A145B7BF4E1F4001487F1016730F99FC6AA080FAE8705B49"
		}]
	}
}
```
到此就得到了vkey

### 获取下载链接

现在我们有了songmid、guid、uin和vkey，就可以随便的下载歌曲啦啦啦~~

同样的，先上网址

`http://dl.stream.qqmusic.qq.com/M800[歌曲的songmid].mp3?vkey=[你的key]&guid=[你的guid]&uin=[你的uin]&fromtag=30`

有一个要说明的是songmid前后的M8000和.mp3以及尾部的[fromtag]，有着如下对应关系

前缀|后缀|fromtag
-|-|-
F000|.flac|53
A000|.ape|66
M800|.mp3|30
M500|.mp3|30

其中M800为320k的mp3，M500为普通的mp3

e.g.最后的url：

`http://dl.stream.qqmusic.qq.com/F000003qKBfB2nc0RX.flac?vkey=35C52C2FF89D10865873F4A70F52190B05DB2C268ECD3BA7E388F1FCC6146F2B75F011F588F09D95D8EBC5FB676A2EE73A349AA9E65266D5&guid=2&uin=1&fromtag=53`

如果成功了应该会变成网页播放器（我的chrome是这样的），如果错误就会弹**403 Forbidden**

到此各种类型的歌曲应该都可以爬下来慢慢听了，从此再也不怕听歌流量不够了。
