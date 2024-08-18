# AICL

#### 1、Prepare environment

A100 + Python 3.10 + torch 2.3.1 + CUDA Version: 12.2

cd bin;

pip install -r requirements.txt



#### 2、Prepare data

The whole ICLB dataset will release after acceptance.

- ##### Data Examples

| Task Type      | Example                                                      |
| -------------- | ------------------------------------------------------------ |
| QA             | {"id":  65248, "messages": [{"role": "user",  "content": "Pick the accurate answer number corresponding to  the provided question and answer candidates.<input>:The sun is  responsible for\npuppies learning new tricks: A\nchildren growing up and  getting old: B\nflowers wilting in a vase: C\nplants sprouting, blooming and  wilting: D\n\n<output>:", "loss": 0}, {"role":  "assistant", "content": "D", "loss":  1}, {"role": "user", "content":  "<input>:When standing miles away from Mount Rushmore\nthe  mountains seem very close: A\nthe mountains are boring: B\nthe mountains look  the same as from up close: C\nthe mountains seem smaller than in photographs:  D\n\n<output>:", "loss": 0}, {"role":  "assistant", "content": "D", "loss":  1},...,{"role": "user", "content":  "<input>:When food is reduced in the stomach\nthe mind needs time  to digest: A\ntake a second to digest what I said: B\nnutrients are being  deconstructed: C\nreader's digest is a body of works:  D\n\n<output>:", "loss": 0}, {"role":  "assistant", "content": "C", "loss":  1}], "resource": "OpenbookQA", "len": 7983} |
| Summarization  | {"id": 23742, "messages": [{"role": "user", "content": "Examine a piece of writing and sum up the primary concepts in a short summary.<input>:By \nSophie Borland\n\nPUBLISHED:\n\n20:07 EST, 15 November 2012\n\n\n \n\nUPDATED:\n\n03:11 EST, 16 November 2012\n\nRising numbers of Britons are suffering burns from hot water bottles, warn experts.\n\nResearchers say they have become increasingly popular in the home as a cheap alternative to turning on the heating.\n\nBut if the bottles are poorly made or the rubber has perished, they can explode without warning during the night.\n\nThis can cause serious burns or scalds which in some cases are so serious that patients require skin grafts.\n\nResearchers say the number of hot water bottles being used in Britain has risen due to the rising cost of the heating\n\nResearchers at Anglia Ruskin University say that the numbers needing hospital treatment for hot water bottle burns has risen in the last two years.\n\nBut they say these admissions only represent a handful of the true numbers suffering injuries as most will not go to hospital.\n\nOne reason for the increase is that people are buying cheap hot water bottles from abroad made from rubber that easily perishes.\n\nFurthermore the researchers say rising numbers of families are using them as a 'cost-effective' way of staying warm in the hope of saving on their energy bills.\n\nQuentin Frew, of Anglia Ruskin University, said: 'Anecdotally we have seen an increase in burns caused by hot water bottles in the last couple of years.\n\n'It could be that more people are using them as a cost-effective way of keeping warm or it could be that people are buying cheaper hot water bottles over the internet from abroad. \n\n'What we have seen at the hospital is only the tip of the iceberg, as the majority of these cases go unreported. People try and manage the burns themselves, often because they are embarrassed about what they have done or the area they have burnt.\n\n'When looking at burns from hot water bottles it is sometimes difficult to say which have been caused by patient misuse and which are due to poor manufacturing standards.\n\n'What is clear is that there is a need to increase awareness of the ability of hot water bottles to cause significant long-term burn injuries and also highlight the precautionary measures that could be taken to prevent such injuries.\n\n'One common problem is people storing them incorrectly, which can cause the rubber to perish.'\n\nThe researchers looked at the medical notes of 50 patients who had suffered burns and scalds from hot water bottles.\n\nThey found that injuries took an average of 25 days to heal - three and a half weeks. And in three of the patients, including two children, the burns were so serious they needed skin grafts.\n\nIn some cases patients were to blame for the injuries as they had filled bottles with boiling water that causes the rubber to wear out.\n\nThe NHS does not compile figures on the numbers of patients needing treatment for hot water bottle burns.\n\nBut last year more than 1,800 were admitted to hospital following injuries caused by hot water or other hot fluids, which would include hot water bottles.\n\n<output>:", "loss": 0}, {"role": "assistant", "content": "Rising numbers of Britons are suffering burns from hot water bottles\nResearchers say numbers needing treatment for burns has risen in lat two years\nFamilies using hot water bottles to save energy bills", "loss": 1},...], "resource": "DAILYMAIL", "len": 7752} |
| Classification | {"id": 28352, "messages": [{"role": "user", "content": "Categorize the following statements into one of these five classifications: {0, 1, 2, 3, 4}.\n\n<input>:Five Stars\n\nBest frothed. I’ve purchased other brands and they all break down within a couple months. Mixpresso lasts.\n\n<output>:", "loss": 0}, {"role": "assistant", "content": "4", "loss": 1}, {"role": "user", "content": "<input>:Good size for short runs.\n\nEasy carry pack. Good size for short runs.\n\n<output>:", "loss": 0}, {"role": "assistant", "content": "4", "loss": 1}, {"role": "user", "content": "<input>:Not as expected\n\nThese are red orange not red\n\n<output>:", "loss": 0}, {"role": "assistant", "content": "1", "loss": 1}, {"role": "user", "content": "<input>:Perfect Bike Bag for non-professionals\n\nI have been looking for a bike bag in order to have my phone available, water bottles, and to store just a few things. This bag came with 3 velcro straps, securing it without jostling as I ride. THe others I looked at were more expensive and didn't have this feature. The \"cone\" down makes it compact instead of a large \" box\" on the front. Aesthetically attractive!! I HIGHLY recommend this product. Almost forgot, the clear pouch at the top is great for maps, seeing calls, and let's not forget the safety - hard to steal, makes it available for calls in case of an emergency, just a very handy feature\n\n<output>:", "loss": 0}, {"role": "assistant", "content": "4", "loss": 1}], "resource": "AmazonReviews", "len": 7911} |
| Reasoning      | {"id": 7938, "messages": [{"role": "user", "content": "Classify the given sentence into one of the following categories: {{\"math\": 0, \"astro-ph\": 1, \"other\": 2, \"hep\": 3, \"cond-mat\": 4, \"quant-ph\": 5, \"cs\": 6, \"stat\": 7, \"eess\": 8, \"q-bio\": 9, \"q-fin\": 10, \"econ\": 11, \"hep-th\": 12, \"gr-qc\": 13, \"cond-mat.stat-mech\": 14, \"astro-ph.SR\": 15, \"cs.CV\": 16, \"math.AP\": 17, \"hep-ph\": 18, \"math.GR\": 19, \"cs.SI\": 20, \"cs.IT\": 21, \"cs.LG\": 22, \"stat.ME\": 23, \"astro-ph.GA\": 24, \"math.ST\": 25, \"cond-mat.mes-hall\": 26, \"cs.CR\": 27, \"cs.CC\": 28, \"econ.EM\": 29, \"math.FA\": 30, \"cs.FL\": 31, \"math-ph\": 32, \"math.DG\": 33, \"q-bio.QM\": 34, \"hep-ex\": 35, \"cond-mat.soft\": 36, \"physics.soc-ph\": 37, \"physics.flu-dyn\": 38, \"eess.SY\": 39, \"nucl-th\": 40, \"cond-mat.supr-con\": 41, \"q-fin.PM\": 42, \"math.CV\": 43, \"astro-ph.EP\": 44, \"q-bio.PE\": 45, \"cs.DB\": 46, \"physics.data-an\": 47, \"astro-ph.CO\": 48, \"math.AG\": 49, \"cond-mat.str-el\": 50, \"physics.geo-ph\": 51, \"math.SG\": 52, \"cs.NI\": 53, \"q-bio.MN\": 54, \"math.OC\": 55, \"cs.CG\": 56, \"math.NT\": 57, \"math.CO\": 58, \"stat.ML\": 59, \"cs.LO\": 60, \"math.AT\": 61, \"cond-mat.dis-nn\": 62, \"math.PR\": 63, \"cond-mat.mtrl-sci\": 64, \"astro-ph.HE\": 65, \"hep-lat\": 66, \"cs.AI\": 67, \"math.DS\": 68, \"math.OA\": 69, \"eess.SP\": 70, \"cs.NE\": 71, \"physics.optics\": 72, \"physics.comp-ph\": 73, \"cs.CY\": 74, \"stat.AP\": 75, \"cs.CL\": 76, \"cond-mat.quant-gas\": 77, \"math.CA\": 78, \"math.QA\": 79, \"physics.acc-ph\": 80, \"math.RA\": 81, \"physics.chem-ph\": 82, \"physics.atom-ph\": 83, \"physics.ins-det\": 84, \"math.CT\": 85, \"physics.space-ph\": 86, \"math.NA\": 87, \"cs.GR\": 88, \"math.GT\": 89, \"cs.RO\": 90, \"astro-ph.IM\": 91, \"math.SP\": 92, \"math.KT\": 93, \"physics.plasm-ph\": 94, \"math.RT\": 95, \"cs.HC\": 96, \"cs.PF\": 97, \"physics.app-ph\": 98, \"cs.IR\": 99, \"cs.DS\": 100, \"physics.bio-ph\": 101, \"cs.SE\": 102, \"cs.DC\": 103, \"q-bio.NC\": 104, \"cs.DL\": 105, \"physics.hist-ph\": 106, \"cs.AR\": 107, \"nlin.CD\": 108, \"physics.ao-ph\": 109, \"physics.pop-ph\": 110, \"chao-dyn\": 111, \"nucl-ex\": 112, \"cs.GT\": 113, \"eess.IV\": 114, \"econ.TH\": 115, \"nlin.SI\": 116, \"physics.ed-ph\": 117, \"math.MG\": 118, \"math.LO\": 119, \"stat.CO\": 120, \"physics.gen-ph\": 121, \"cond-mat.other\": 122, \"cs.DM\": 123, \"econ.GN\": 124, \"physics.med-ph\": 125, \"dg-ga\": 126, \"math.AC\": 127, \"q-fin.RM\": 128, \"physics.class-ph\": 129, \"cs.MS\": 130, \"q-bio.BM\": 131, \"math.GN\": 132, \"cs.MM\": 133, \"cs.SY\": 134, \"physics.atm-clus\": 135, \"math.GM\": 136, \"q-fin.ST\": 137, \"cs.NA\": 138, \"q-fin.CP\": 139, \"cs.SD\": 140, \"q-alg\": 141, \"eess.AS\": 142, \"nlin.AO\": 143, \"cs.PL\": 144, \"alg-geom\": 145, \"cs.OH\": 146, \"q-fin.GN\": 147, \"math.HO\": 148, \"q-fin.PR\": 149, \"cs.CE\": 150, \"q-bio.GN\": 151, \"q-fin.TR\": 152, \"cs.ET\": 153, \"cs.MA\": 154, \"stat.OT\": 155, \"nlin.PS\": 156, \"mtrl-th\": 157, \"q-bio.TO\": 158, \"q-fin.MF\": 159, \"patt-sol\": 160, \"cs.SC\": 161, \"cmp-lg\": 162, \"chem-ph\": 163, \"solv-int\": 164, \"acc-phys\": 165, \"cs.OS\": 166, \"q-bio.OT\": 167, \"q-bio.CB\": 168, \"q-bio.SC\": 169, \"funct-an\": 170, \"q-fin.EC\": 171, \"cs.GL\": 172, \"nlin.CG\": 173, \"adap-org\": 174, \"comp-gas\": 175, \"plasm-ph\": 176, \"atom-ph\": 177, \"supr-con\": 178, \"ao-sci\": 179}}. The output should be the corresponding number for the matched label.\n\n<input>:Seasonal hydrogen storage decisions under constrained electricity\n  distribution capacity\n\n<output>:", "loss": 0},{"role": "assistant", "content": "39", "loss": 1},...,{"role": "user", "content": "<input>:Entropy driven formation of a half-quantum vortex lattice\n\n<output>:", "loss": 0}, {"role": "assistant", "content": "4", "loss": 1}, {"role": "user", "content": "<input>:Pressure-induced reemergence of superconductivity in BaIr2Ge7 and\n  Ba3Ir4Ge16 with cage structures\n\n<output>:", "loss": 0}, {"role": "assistant", "content": "41", "loss": 1}], "resource": "ArxivClusteringS2S", "len": 7995} |
| Retrieval      | {"id": 43555, "messages": [{"role": "user", "content": "Select the most pertinent text from a collection of 10 that best corresponds to one of the specified predefined labels.\n\n<input>:蒸子广场舞5211\ncandidates:\n{\"0\": \"kiboomers英文儿歌 光明节 少儿 英语 2019 hanukkah song for kids chanukah song for kids\", \"1\": \"六小龄童 西游记 23国语1982共25集\", \"2\": \"2018年全国青少年武术套路锦标赛 C组 男子剑术 频道名: 体育 日期: 2019\", \"3\": \"舞蹈 印度风情 印度歌曲跳舞曲 flv 1\", \"4\": \"70年代dj音乐\", \"5\": \"dm动漫大杂烩小朋友儿歌 爱我你就抱抱我 mp4\", \"6\": \"武松大闹狮子楼 电影 >贺志刚,韩云珍,赵琛 bloodshed om the lion chamber\", \"7\": \"2001年10月央视动画城 主持人达达狼 小蜻蜓 旧版主题曲 留在心中\", \"8\": \"小米跳广场舞\", \"9\": \"燕子广场舞5211 第2季 体育 2020\"}\n\n<output>:", "loss": 0}, {"role": "assistant", "content": "燕子广场舞5211 第2季 体育 2020", "loss": 1},..., {"role": "user", "content": "<input>:太妃升职计电视剧\ncandidates:\n{\"0\": \"太子妃升职记 为了一个破落女子 你竟然敢打太子妃耳光\", \"1\": \"英雄联>盟2017德玛西亚杯 冬季赛 blg vs rng bo3\", \"2\": \"小宇热游 宇哥疯狂的搞破坏铁板都看不下去了 第288期\", \"3\": \"ps5 新老平台对比 最终幻想7 重制版 第二篇章特别预告\", \"4\": \"小学生大闹gta5 013再蠢再笨再坏的儿子也要救啊\", \"5\": \"2000年参加全国大专辩论赛\", \"6\": \"2002年1月x日cctv 1广告片段\", \"7\": \"58速运给大家拜年啦\", \"8\": \"猴姆独家 omfg 碧昂斯新歌来咯 beyonce 助阵 megan thee stallion 热单savage混音版饭制歌词mv大首播 还是这么上头\", \"9\": \"一对男女抢银行欲私奔不幸撞山 男子被水流冲走 gtaol 太平洋 上\"}\n\n<output>:", "loss": 0}, {"role": "assistant", "content": "太子妃升职记为了一个破落女子 你竟然敢打太子妃耳光", "loss": 1}], "resource": "VideoRetrieval", "len": 7822} |
| Reranking      | {"id": 29728, "messages": [{"role": "user", "content": "Please reorder the candidates based on the relevance to the input, ensuring that the one with the highest relevance is listed as the first . Please return the response in JSON format.<input>:ubuntu download errors ?\ncandidates:\n{\"0\": \"update errors on ubuntu- i get this message\", \"1\": \"problem trying to upgrade 10.04 to 12.04\", \"2\": \"can i download the new version and burn it to a cd and install it without reformating the hard drive ?\", \"3\": \"ca n't complete my download\", \"4\": \"need ubuntu 11.10 download link\", \"5\": \"why i am getting `` 404 not found '' errors for a ppa when updating ?\", \"6\": \"nothing working properly\", \"7\": \"ubuntu 12.04 server install fails with debootstrap warning\"}\n\n<output>:", "loss": 0}, {"role": "assistant", "content": "{\"0\": \"ca n't complete my download\", \"1\": \"nothing working properly\", \"2\": \"update errors on ubuntu- i get this message\", \"3\": \"ubuntu 12.04 server install fails with debootstrap warning\", \"4\": \"problem trying to upgrade 10.04 to 12.04\", \"5\": \"why i am getting `` 404 not found '' errors for a ppa when updating ?\", \"6\": \"need ubuntu 11.10 download link\", \"7\": \"can i download the new version and burn it to a cd and install it without reformating the hard drive ?\"}", "loss": 1},..., {"role": "user", "content": "<input>:how do i remove ubuntu and install windows 7 ?\ncandidates:\n{\"0\": \"how to remove ubuntu 11.10 after it is installed alongside windows\", \"1\": \"how to remove ubuntu from my windows 7 ?\", \"2\": \"how to remove ubuntu 12.04 ?\", \"3\": \"remove ubuntu from dual boot windows 7 both in same drive\", \"4\": \"remove ubuntu partition\", \"5\": \"how to make windows the default os in grub menu ?\", \"6\": \"unable to boot to windows after installing ubuntu\", \"7\": \"i want to remove windows 8 and windows 7 from my triple boot with ubuntu 12.04\", \"8\": \"how to install windows 7 on dell inspiron 15- 3521 laptop\", \"9\": \"after formatting windows 7 there is still dual-boot screen\"}\n\n<output>:", "loss": 0}, {"role": "assistant", "content": "{\"0\": \"unable to boot to windows after installing ubuntu\", \"1\": \"how to remove ubuntu 11.10 after it is installed alongside windows\", \"2\": \"remove ubuntu partition\", \"3\": \"how to make windows the default os in grub menu ?\", \"4\": \"how to remove ubuntu from my windows 7 ?\", \"5\": \"remove ubuntu from dual boot windows 7 both in same drive\", \"6\": \"how to install windows 7 on dell inspiron 15- 3521 laptop\", \"7\": \"after formatting windows 7 there is still dual-boot screen\", \"8\": \"i want to remove windows 8 and windows 7 from my triple boot with ubuntu 12.04\", \"9\": \"how to remove ubuntu 12.04 ?\"}", "loss": 1}], "resource": "askubuntudupquestions-reranking", "len": 7856} |
| Clustering     | {"id": 7938, "messages": [{"role": "user", "content": "Classify the given sentence into one of the following categories: {{\"math\": 0, \"astro-ph\": 1, \"other\": 2, \"hep\": 3, \"cond-mat\": 4, \"quant-ph\": 5, \"cs\": 6, \"stat\": 7, \"eess\": 8, \"q-bio\": 9, \"q-fin\": 10, \"econ\": 11, \"hep-th\": 12, \"gr-qc\": 13, \"cond-mat.stat-mech\": 14, \"astro-ph.SR\": 15, \"cs.CV\": 16, \"math.AP\": 17, \"hep-ph\": 18, \"math.GR\": 19, \"cs.SI\": 20, \"cs.IT\": 21, \"cs.LG\": 22, \"stat.ME\": 23, \"astro-ph.GA\": 24, \"math.ST\": 25, \"cond-mat.mes-hall\": 26, \"cs.CR\": 27, \"cs.CC\": 28, \"econ.EM\": 29, \"math.FA\": 30, \"cs.FL\": 31, \"math-ph\": 32, \"math.DG\": 33, \"q-bio.QM\": 34, \"hep-ex\": 35, \"cond-mat.soft\": 36, \"physics.soc-ph\": 37, \"physics.flu-dyn\": 38, \"eess.SY\": 39, \"nucl-th\": 40, \"cond-mat.supr-con\": 41, \"q-fin.PM\": 42, \"math.CV\": 43, \"astro-ph.EP\": 44, \"q-bio.PE\": 45, \"cs.DB\": 46, \"physics.data-an\": 47, \"astro-ph.CO\": 48, \"math.AG\": 49, \"cond-mat.str-el\": 50, \"physics.geo-ph\": 51, \"math.SG\": 52, \"cs.NI\": 53, \"q-bio.MN\": 54, \"math.OC\": 55, \"cs.CG\": 56, \"math.NT\": 57, \"math.CO\": 58, \"stat.ML\": 59, \"cs.LO\": 60, \"math.AT\": 61, \"cond-mat.dis-nn\": 62, \"math.PR\": 63, \"cond-mat.mtrl-sci\": 64, \"astro-ph.HE\": 65, \"hep-lat\": 66, \"cs.AI\": 67, \"math.DS\": 68, \"math.OA\": 69, \"eess.SP\": 70, \"cs.NE\": 71, \"physics.optics\": 72, \"physics.comp-ph\": 73, \"cs.CY\": 74, \"stat.AP\": 75, \"cs.CL\": 76, \"cond-mat.quant-gas\": 77, \"math.CA\": 78, \"math.QA\": 79, \"physics.acc-ph\": 80, \"math.RA\": 81, \"physics.chem-ph\": 82, \"physics.atom-ph\": 83, \"physics.ins-det\": 84, \"math.CT\": 85, \"physics.space-ph\": 86, \"math.NA\": 87, \"cs.GR\": 88, \"math.GT\": 89, \"cs.RO\": 90, \"astro-ph.IM\": 91, \"math.SP\": 92, \"math.KT\": 93, \"physics.plasm-ph\": 94, \"math.RT\": 95, \"cs.HC\": 96, \"cs.PF\": 97, \"physics.app-ph\": 98, \"cs.IR\": 99, \"cs.DS\": 100, \"physics.bio-ph\": 101, \"cs.SE\": 102, \"cs.DC\": 103, \"q-bio.NC\": 104, \"cs.DL\": 105, \"physics.hist-ph\": 106, \"cs.AR\": 107, \"nlin.CD\": 108, \"physics.ao-ph\": 109, \"physics.pop-ph\": 110, \"chao-dyn\": 111, \"nucl-ex\": 112, \"cs.GT\": 113, \"eess.IV\": 114, \"econ.TH\": 115, \"nlin.SI\": 116, \"physics.ed-ph\": 117, \"math.MG\": 118, \"math.LO\": 119, \"stat.CO\": 120, \"physics.gen-ph\": 121, \"cond-mat.other\": 122, \"cs.DM\": 123, \"econ.GN\": 124, \"physics.med-ph\": 125, \"dg-ga\": 126, \"math.AC\": 127, \"q-fin.RM\": 128, \"physics.class-ph\": 129, \"cs.MS\": 130, \"q-bio.BM\": 131, \"math.GN\": 132, \"cs.MM\": 133, \"cs.SY\": 134, \"physics.atm-clus\": 135, \"math.GM\": 136, \"q-fin.ST\": 137, \"cs.NA\": 138, \"q-fin.CP\": 139, \"cs.SD\": 140, \"q-alg\": 141, \"eess.AS\": 142, \"nlin.AO\": 143, \"cs.PL\": 144, \"alg-geom\": 145, \"cs.OH\": 146, \"q-fin.GN\": 147, \"math.HO\": 148, \"q-fin.PR\": 149, \"cs.CE\": 150, \"q-bio.GN\": 151, \"q-fin.TR\": 152, \"cs.ET\": 153, \"cs.MA\": 154, \"stat.OT\": 155, \"nlin.PS\": 156, \"mtrl-th\": 157, \"q-bio.TO\": 158, \"q-fin.MF\": 159, \"patt-sol\": 160, \"cs.SC\": 161, \"cmp-lg\": 162, \"chem-ph\": 163, \"solv-int\": 164, \"acc-phys\": 165, \"cs.OS\": 166, \"q-bio.OT\": 167, \"q-bio.CB\": 168, \"q-bio.SC\": 169, \"funct-an\": 170, \"q-fin.EC\": 171, \"cs.GL\": 172, \"nlin.CG\": 173, \"adap-org\": 174, \"comp-gas\": 175, \"plasm-ph\": 176, \"atom-ph\": 177, \"supr-con\": 178, \"ao-sci\": 179}}. The output should be the corresponding number for the matched label.\n\n<input>:Seasonal hydrogen storage decisions under constrained electricity\n  distribution capacity\n\n<output>:", "loss": 0},{"role": "assistant", "content": "39", "loss": 1},...,{"role": "user", "content": "<input>:Entropy driven formation of a half-quantum vortex lattice\n\n<output>:", "loss": 0}, {"role": "assistant", "content": "4", "loss": 1}, {"role": "user", "content": "<input>:Pressure-induced reemergence of superconductivity in BaIr2Ge7 and\n  Ba3Ir4Ge16 with cage structures\n\n<output>:", "loss": 0}, {"role": "assistant", "content": "41", "loss": 1}], "resource": "ArxivClusteringS2S", "len": 7995} |

cd bin;

python balance_training_data.py;



#### 3、Train

cd bin;

sh train.sh;



#### 4、Test

cd bin;

sh run_inference.sh;



#### 5、Eval

cd bin;

python evaluation.py test.jsonl predict.jsonl task_type task_name;





