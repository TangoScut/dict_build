构建词库
==========

从原始文本中，自动构建词库，目前只适用于中文。参考：

http://www.matrix67.com/blog/archives/5044

###new in 0.0.2
1. 直接导入[java-merge-sort](https://github.com/cowtowncoder/java-merge-sort)源码, thx[@cowtowncoder](https://github.com/cowtowncoder)
2. 将之前的maven项目，转变为一个gradle项目，方便打包使用。

###成词条件
1. 互信息
2. 左右熵
3. 位置成词概率
4. ngram 频率

###运行方法
1. [下载](https://github.com/sing1ee/dict_build/blob/master/dict_build-0.0.2.tar?raw=true)或者gradle distTar打包程序
2. 解压dict_build-x.x.x.tar
3. 解压之后,进入bin. 运行:./dict_build 你的数据文件的绝对路径
4. 结束之后,在数据文件同目录有文件:words_sort.data
5. 四列分别为:词,词频,互信息,左右熵,位置成词概率.


###示例

####《金瓶梅》抽取结果
```shell
西门庆  4754    6.727920454563199   2.0315193024276885  0.17472535684926388
月娘    1829    6.491853096329675   2.3714166640957095  0.22135096835144072
敬济    906 9.084808387804362   2.554594603718855   0.14485683987274656
春梅    799 8.134426320220927   2.7880175589451714  0.16484505593416485
玳安    796 8.228818690495881   2.865686193737731   0.11791820110723605
后边    617 6.6293566200796095  4.008365154080131   0.2160373686259245
玉楼    594 7.977279923499917   2.27346284978306    0.27518689925240297
明日    580 6.189824558880018   2.705423396095033   0.1774535638537181
两银子  458 6.129283016944967   2.351100547282295   0.3809078896437581
小厮    454 7.257387842692652   3.945653525477103   0.16666666666666666
打发    444 6.870364719583405   3.694604352707633   0.18409496065046307
如今    410 6.643856189774725   2.1460777430093394  0.1780766096169519
淫妇    382 7.768184324776926   3.277903508489837   0.2555205047318612
桂姐    371 7.584962500721156   2.5922046565140424  0.36255305256284687
老婆    331 6.266786540694902   3.5783015008688523  0.3758007117437722
衣服    309 8.90388184573618    2.786139685416002   0.13284518828451883
丫头    297 7.383704292474053   4.291010086795063   0.21875
潘金莲  288 8.276124405274238   2.4955186567189194  0.35333669524289796
昨日    285 6.857980995127572   2.6387249970833997  0.1774535638537181
王婆    284 7.1799090900149345  2.3129267619188907  0.3758007117437722
```

####《西游记》抽取结果
```shell
八戒    1807    7.88874324889826    2.00952580557629    0.36441586280814575
师父    1632    7.507794640198696   3.745294449785798   0.1371395690812608
大圣    1270    6.599912842187128   2.7790919785432147  0.13128460061010055
唐僧    1003    7.076815597050832   4.350465172292435   0.43277723258096173
菩萨    765 9.471675214392045   3.6013747138664756  0.15910495734948696
妖精    634 7.199672344836364   3.1817261900583627  0.13134411600669268
徒弟    439 8.060695931687555   2.498555429145656   0.15553809897879026
兄弟    284 7.845490050944376   2.93037668783551    0.16085578446909668
宝贝    283 9.319672120946995   2.616164396748633   0.15108220492589827
今日    282 6.714245517666122   2.1303069812971214  0.1774535638537181
取经    263 7.539158811108032   2.663944888382171   0.10181178023912565
如今    259 6.189824558880018   2.056188859866133   0.1780766096169519
认得    223 6.357552004618085   2.9543379335926954  0.2326782564877803
东土    212 8.422064766172811   3.326253983395916   0.14745277618775043
孙大圣  202 6.022367813028454   2.4886576514017107  0.13128460061010055
变作    189 7.554588851677638   3.0713596792578635  0.23452975920036348
玉帝    189 8.912889336229961   2.973106046717708   0.27518689925240297
土地    179 7.499845887083206   3.1206506190132566  0.2819944064037033
欢喜    173 8.861086905995393   2.184918471204895   0.31727272727272726
贫僧    170 7.400879436282184   2.0731236036504477  0.43277723258096173
```

#### 拉勾JD预料抽取结果
```shell
工作	641962	11.645208082774683	4.083574124851783	0.11247281022865935
开发	348538	14.031184262140844	4.37645153459778	0.18409496065046307
相关	300517	10.477758266443889	5.038915743418073	0.1758213331033888
合作	159688	10.397674632948268	3.9963476653135794	0.19498851077798446
专业	158831	10.712527000439824	3.152041650598071	0.2640750670241287
测试	158179	13.65362883340751	4.464104436545589	0.18344308560677328
互联网	148818	16.106992250086762	3.9556191209604314	0.407386403912951
活动	131099	10.391243589427443	3.9155422678129406	0.20137250696976194
维护	120316	12.681677655209691	3.2400117935377266	0.1960306406685237
问题	112116	9.159871336778389	2.314215135279833	0.20283174185051037
优化	109563	11.324180546618742	4.331660381832997	0.2456782591010779
营销	105845	14.36850646150769	5.097001962525406	0.14961371773129828
平台	100783	9.002815015607053	4.443804901153697	0.2877423571272965
培训	93204	9.041659151637216	3.8898570467819824	0.13345998575160295
资源	90339	8.651051691178928	4.063430372719874	0.14695817490494298
相关专业	87545	8.988684686772165	2.4897196388075598	0.2905199904149232
网站	87182	8.92184093707449	5.465843476701055	0.21266038137095059
独立	86111	9.074141462752506	3.1456261690072957	0.19050261614079594
一定	83798	8.335390354693924	2.107303660112154	0.26157299167679793
流程	83165	9.321928094887362	2.5509378861028074	0.2063141084699957
网络	82742	9.087462841250339	4.681429111504988	0.21266038137095059
优秀	74600	9.370687406807217	2.0756995478573135	0.2899855507391353
信息	71009	9.820178962415188	4.2602697278449755	0.18863532864443658
媒体	67533	10.556506054671928	4.615376861300178	0.17976710334788937
编写	64337	7.960001932068081	3.482400585501417	0.265625
思维	62351	8.741466986401146	2.4320664807326646	0.15396736072031514
规划	59733	7.851749041416057	2.936854928368285	0.14166201896263245
移动	59671	10.10459875356437	3.4421932833155653	0.20137250696976194
渠道	59072	9.513727595952437	4.597891463808354	0.23578595317725753
关系	58483	8.348728154231077	2.4369558675502927	0.3170022612253688
积极	57295	9.044394119358454	2.763249521041074	0.1746848469256496
实施	56645	7.781359713524661	4.371966846513886	0.15944453739334113
福利	55732	8.475733430966399	2.4036919305145426	0.20908952728378172
其他	55665	8.434628227636725	2.9614863103296867	0.15943975441289332
功能	55087	7.787902559391432	4.1663586610392755	0.18097560975609756
代码	52431	7.88874324889826	3.876917512626917	0.2135697048449972
微信	49143	8.945443836377912	3.6868130380800643	0.18215857916308253
企业	48799	9.422064766172813	5.568662443510237	0.2905199904149232
提升	48446	8.233619676759702	3.7390647282620666	0.29750778816199375
质量	47918	10.861862340059153	3.391825261582227	0.10921827734437191
人员	47109	7.774787059601174	5.249783964892326	0.13589632038101343
数据库	45445	8.290018846932618	4.123423571610193	0.2640569395017794
商务	44047	8.189824558880018	3.44858516585648	0.12901085044961344
主动	42628	13.815583433851023	2.5049637884195137	0.1968791796700847
创意	41768	14.396470993910388	4.115068825929573	0.30544056771141337
工具	40227	9.927777962082342	2.208874047820781	0.11247281022865935
等相关	39230	11.919608238603255	3.0330398736413557	0.1758213331033888
提出	38741	10.179909090014934	4.46446156782086	0.13053040103492886
各类	38309	8.344295907915816	5.136417986953123	0.3969948596283116
操作	37061	9.06339508128851	4.676836974292029	0.23452975920036348
收集	36600	8.800899899920305	2.797691452951563	0.11388512456999896
过程	36534	8.214319120800766	2.5633950372758565	0.2063141084699957
数据分析	36081	8.442943495848729	3.5589033442862585	0.2640569395017794
```