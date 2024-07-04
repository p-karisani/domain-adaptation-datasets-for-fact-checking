These are two datasets used in the paper below: <br/>
*Fact Checking Beyond Training Set*, Payam Karisani, Heng Ji. NAACL 2024. [Link](https://arxiv.org/abs/2403.18671)

**Data Description** <br/>
This repo contains two datasets. One called Snopes, and another one called MultiFC. Each dataset consists of a set of claims, and also a set of relevant evidence documents to each claim. The Snopes dataset was crawled from the Snopes fact checking website. The MultiFC dataset was constructed by aggregating several other fact checking datasets, and using a web search engine to collect their evidence documents.

Important Note: These two datasets were originally published in these two papers: [Paper 1](https://arxiv.org/abs/1911.01214) and [Paper 2](https://arxiv.org/abs/1909.03242). But They are not suitable for domain adaptation in their original format. We proposed an algorithm, after a few pre-processing steps, to prepare them for our experiments (please see our paper for the details). If you are using this data please make sure to cite those two papers as well. <br/>

Summary of the MultiFC dataset:
| Domain | Claim # | Refute | Support |
| ------ | ----- | -------- | -------- |
| Arts | 3,788 | 3,434 | 354 |
| Business | 1,943 | 1,007 | 936 |
| Misc | 7,968 | 5,351 | 2,617 |
| Politics | 9,350 | 6,301 | 3,049 |
| Sensitive | 2,180 | 1,555 | 625 |

Summary of the Snopes dataset:
| Domain | Claim # | Neutral | Refute | Support |
| ------ | ----- | -------- | -------- | -------- |
| General | 4,190 | 755 | 2,643 | 792 |
| News | 1,620 | 348 | 1,041 | 231 |

**Data Format** <br/>
Each directory contains two files, "claims" and "evidence". The filenames are self-explanatory. If a file is too big, it was zipped to facilitate the file transfer. Each line in the file "claims" (or "evidence") is dedicated to one claim (or evidence document). They are stored in Json format. 

The attributes of each claim are:
1) id (String)
2) label (Int)
   * In the MultiFC dataset, (0 = Refute) and (1 = Support).
   * In the Snopes dataset, (0 = Neutral), (1 = Refute), and (2 = Support).
4) domain (String)
5) text (String) 

The attributes of each evidence document are:
1) id (String) 
2) ref_id (String): The claim id that this evidence document is relevant to
3) label (Int): You can ignore this field
4) text (String)
---------
If you are using this data, please cite the paper below:

```
@inproceedings{karisani-ji-2024-fact,
    title = "Fact Checking Beyond Training Set",
    author = "Karisani, Payam  and
      Ji, Heng",
    booktitle = "Proceedings of the 2024 Conference of the NAACL: Human Language Technologies (Volume 1: Long Papers)",
    month = jun,
    year = "2024",
    address = "Mexico City, Mexico",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2024.naacl-long.124",
    pages = "2247--2261",
}
```
