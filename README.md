
<img src="https://github.com/natasha/natasha-logos/blob/master/corus.svg">

[![Build Status](https://travis-ci.org/natasha/corus.svg?branch=master)](https://travis-ci.org/natasha/corus) [![Coverage Status](https://coveralls.io/repos/github/natasha/corus/badge.svg?branch=master)](https://coveralls.io/github/natasha/corus?branch=master)

Links to publicly available Russian corpora + code for loading and parsing. <a href="#reference">20+ datasets, 350Gb+ of text</a>.

## Usage

For example lets use <a href="https://github.com/yutkin/Lenta.Ru-News-Dataset">dump of lenta.ru by @yutkin</a>. Manually download the archive (link in the <a href="#reference">Reference</a> section):
```bash
wget https://github.com/yutkin/Lenta.Ru-News-Dataset/releases/download/v1.0/lenta-ru-news.csv.gz
```

Use `corus` to load the data:

```python
>>> from corus import load_lenta

>>> path = 'lenta-ru-news.csv.gz'
>>> records = load_lenta(path)
>>> next(records)

LentaRecord(
    url='https://lenta.ru/news/2018/12/14/cancer/',
    title='Названы регионы России с\xa0самой высокой смертностью от\xa0рака',
    text='Вице-премьер по социальным вопросам Татьяна Голикова рассказала, в каких регионах России зафиксирована наиболее высокая смертность от рака, сооб...',
    topic='Россия',
    tags='Общество'
)
```

Iterate over texts:

```python
>>> records = load_lenta(path)
>>> for record in records:
...     text = record.text
...     ...

```

For links to other datasets and their loaders see the <a href="#reference">Reference</a> section.

## Install

`corus` supports Python 2.7+, 3.4+ и PyPy 2, 3.

```bash
$ pip install corus
```

## Reference

<!--- metas --->
<table>
<tr>
<th>Dataset</th>
<th>API <code>from corus import</code></th>
<th>Tags</th>
<th>Texts</th>
<th>Uncompressed</th>
<th>Description</th>
</tr>
<tr>
<td>
<a href="https://github.com/yutkin/Lenta.Ru-News-Dataset">Lenta.ru</a>
</td>
<td>
<a name="load_lenta"></a>
<code><a href="https://nbviewer.jupyter.org/github/natasha/corus/blob/master/docs.ipynb#load_lenta">load_lenta</a></code>
</td>
<td>
<code>news</code>
</td>
<td align="right">
739&nbsp;351
</td>
<td align="right">
1.66 Gb
</td>
<td>
Dump of lenta.ru
</br>
</br>
<code>wget https://github.com/yutkin/Lenta.Ru-News-Dataset/releases/download/v1.0/lenta-ru-news.csv.gz</code>
</td>
</tr>
<tr>
<td>
<a href="https://russe.nlpub.org/downloads/">Lib.rus.ec</a>
</td>
<td>
<a name="load_librusec"></a>
<code><a href="https://nbviewer.jupyter.org/github/natasha/corus/blob/master/docs.ipynb#load_librusec">load_librusec</a></code>
</td>
<td>
<code>lit</code>
</td>
<td align="right">
301&nbsp;871
</td>
<td align="right">
144.92 Gb
</td>
<td>
Dump of lib.rus.ec prepared for RUSSE workshop
</br>
</br>
<code>wget http://panchenko.me/data/russe/librusec_fb2.plain.gz</code>
</td>
</tr>
<tr>
<td>
<a href="https://github.com/RossiyaSegodnya/ria_news_dataset">Rossiya Segodnya</a>
</td>
<td>
<a name="load_ria_raw"></a>
<code><a href="https://nbviewer.jupyter.org/github/natasha/corus/blob/master/docs.ipynb#load_ria_raw">load_ria_raw</a></code>
</br>
<a name="load_ria"></a>
<code><a href="https://nbviewer.jupyter.org/github/natasha/corus/blob/master/docs.ipynb#load_ria">load_ria</a></code>
</td>
<td>
<code>news</code>
</td>
<td align="right">
1&nbsp;003&nbsp;869
</td>
<td align="right">
3.70 Gb
</td>
<td>
<code>wget https://github.com/RossiyaSegodnya/ria_news_dataset/raw/master/ria.json.gz</code>
</td>
</tr>
<tr>
<td>
<a href="https://github.com/dialogue-evaluation/factRuEval-2016/">factRuEval-2016</a>
</td>
<td>
<a name="load_factru"></a>
<code><a href="https://nbviewer.jupyter.org/github/natasha/corus/blob/master/docs.ipynb#load_factru">load_factru</a></code>
</td>
<td>
<code>ner</code>
<code>news</code>
</td>
<td align="right">
254
</td>
<td align="right">
969.27 Kb
</td>
<td>
Manual PER, LOC, ORG markup prepared for 2016 Dialog competition.
</br>
</br>
<code>wget https://github.com/dialogue-evaluation/factRuEval-2016/archive/master.zip</code>
</br>
<code>unzip master.zip</code>
</br>
<code>rm master.zip</code>
</td>
</tr>
<tr>
<td>
<a href="https://www.researchgate.net/publication/262203599_Introducing_Baselines_for_Russian_Named_Entity_Recognition">Gareev</a>
</td>
<td>
<a name="load_gareev"></a>
<code><a href="https://nbviewer.jupyter.org/github/natasha/corus/blob/master/docs.ipynb#load_gareev">load_gareev</a></code>
</td>
<td>
<code>ner</code>
<code>news</code>
</td>
<td align="right">
97
</td>
<td align="right">
455.02 Kb
</td>
<td>
Manual PER, ORG markup.
</br>
</br>
Email Rinat Gareev (gareev-rm@yandex.ru) ask for dataset
</br>
<code>tar -xvf rus-ner-news-corpus.iob.tar.gz</code>
</br>
<code>rm rus-ner-news-corpus.iob.tar.gz</code>
</td>
</tr>
<tr>
<td>
<a href="http://www.labinform.ru/pub/named_entities/">Collection5</a>
</td>
<td>
<a name="load_ne5"></a>
<code><a href="https://nbviewer.jupyter.org/github/natasha/corus/blob/master/docs.ipynb#load_ne5">load_ne5</a></code>
</td>
<td>
<code>ner</code>
<code>news</code>
</td>
<td align="right">
1&nbsp;000
</td>
<td align="right">
2.96 Mb
</td>
<td>
News articles with manual PER, LOC, ORG markup.
</br>
</br>
<code>wget http://www.labinform.ru/pub/named_entities/collection5.zip</code>
</br>
<code>unzip collection5.zip</code>
</br>
<code>rm collection5.zip</code>
</td>
</tr>
<tr>
<td>
<a href="https://www.aclweb.org/anthology/I17-1042">WiNER</a>
</td>
<td>
<a name="load_wikiner"></a>
<code><a href="https://nbviewer.jupyter.org/github/natasha/corus/blob/master/docs.ipynb#load_wikiner">load_wikiner</a></code>
</td>
<td>
<code>ner</code>
</td>
<td align="right">
203&nbsp;287
</td>
<td align="right">
36.15 Mb
</td>
<td>
Sentences from Wiki auto annotated with PER, LOC, ORG tags.
</br>
</br>
<code>wget https://github.com/dice-group/FOX/raw/master/input/Wikiner/aij-wikiner-ru-wp3.bz2</code>
</td>
</tr>
<tr>
<td>
<a href="http://bsnlp.cs.helsinki.fi/shared_task.html">BSNLP-2019</a>
</td>
<td>
<a name="load_bsnlp"></a>
<code><a href="https://nbviewer.jupyter.org/github/natasha/corus/blob/master/docs.ipynb#load_bsnlp">load_bsnlp</a></code>
</td>
<td>
<code>ner</code>
</td>
<td align="right">
464
</td>
<td align="right">
1.16 Mb
</td>
<td>
Markup prepared for 2019 BSNLP Shared Task
</br>
</br>
<code>wget http://bsnlp.cs.helsinki.fi/TRAININGDATA_BSNLP_2019_shared_task.zip</code>
</br>
<code>wget http://bsnlp.cs.helsinki.fi/TESTDATA_BSNLP_2019_shared_task.zip</code>
</br>
<code>unzip TRAININGDATA_BSNLP_2019_shared_task.zip</code>
</br>
<code>unzip TESTDATA_BSNLP_2019_shared_task.zip -d test_pl_cs_ru_bg</code>
</br>
<code>rm TRAININGDATA_BSNLP_2019_shared_task.zip TESTDATA_BSNLP_2019_shared_task.zip</code>
</td>
</tr>
<tr>
<td>
<a href="http://ai-center.botik.ru/Airec/index.php/ru/collections/28-persons-1000">Persons-1000</a>
</td>
<td>
<a name="load_persons"></a>
<code><a href="https://nbviewer.jupyter.org/github/natasha/corus/blob/master/docs.ipynb#load_persons">load_persons</a></code>
</td>
<td>
<code>ner</code>
<code>news</code>
</td>
<td align="right">
1&nbsp;000
</td>
<td align="right">
2.96 Mb
</td>
<td>
PER 
</br>
</br>
<code>wget http://ai-center.botik.ru/Airec/ai-resources/Persons-1000.zip</code>
</td>
</tr>
<tr>
<td>
<a href="http://study.mokoron.com/">Mokoron Russian Twitter Corpus</a>
</td>
<td>
<a name="load_mokoron"></a>
<code><a href="https://nbviewer.jupyter.org/github/natasha/corus/blob/master/docs.ipynb#load_mokoron">load_mokoron</a></code>
</td>
<td>
<code>social</code>
</td>
<td align="right">
17&nbsp;633&nbsp;417
</td>
<td align="right">
1.86 Gb
</td>
<td>
Russian tweets.
</br>
</br>
Manually download https://www.dropbox.com/s/9egqjszeicki4ho/db.sql
</td>
</tr>
<tr>
<td>
<a href="https://dumps.wikimedia.org/">Wikipedia</a>
</td>
<td>
<a name="load_wiki"></a>
<code><a href="https://nbviewer.jupyter.org/github/natasha/corus/blob/master/docs.ipynb#load_wiki">load_wiki</a></code>
</td>
<td>
</td>
<td align="right">
1&nbsp;541&nbsp;401
</td>
<td align="right">
12.94 Gb
</td>
<td>
Russian Wiki dump.
</br>
</br>
<code>wget https://dumps.wikimedia.org/ruwiki/latest/ruwiki-latest-pages-articles.xml.bz2</code>
</td>
</tr>
<tr>
<td>
<a href="https://tatianashavrina.github.io/taiga_site/">Taiga</a>
</td>
<td colspan="5">
Large collection of Russian texts from various sources: news sites, magazines, literacy, social networks.
</br>
</br>
<code>wget https://linghub.ru/static/Taiga/retagged_taiga.tar.gz</code>
</br>
<code>tar -xzvf retagged_taiga.tar.gz</code>
</td>
</tr>
<tr>
<td>
Arzamas
</td>
<td>
<a name="load_taiga_arzamas"></a>
<code><a href="https://nbviewer.jupyter.org/github/natasha/corus/blob/master/docs.ipynb#load_taiga_arzamas">load_taiga_arzamas</a></code>
</td>
<td>
<code>news</code>
</td>
<td align="right">
311
</td>
<td align="right">
4.50 Mb
</td>
<td>
Dump of arzamas.academy.
</td>
</tr>
<tr>
<td>
Fontanka
</td>
<td>
<a name="load_taiga_fontanka"></a>
<code><a href="https://nbviewer.jupyter.org/github/natasha/corus/blob/master/docs.ipynb#load_taiga_fontanka">load_taiga_fontanka</a></code>
</td>
<td>
<code>news</code>
</td>
<td align="right">
342&nbsp;683
</td>
<td align="right">
786.23 Mb
</td>
<td>
Dump of fontanka.ru.
</td>
</tr>
<tr>
<td>
Interfax
</td>
<td>
<a name="load_taiga_interfax"></a>
<code><a href="https://nbviewer.jupyter.org/github/natasha/corus/blob/master/docs.ipynb#load_taiga_interfax">load_taiga_interfax</a></code>
</td>
<td>
<code>news</code>
</td>
<td align="right">
46&nbsp;429
</td>
<td align="right">
77.55 Mb
</td>
<td>
Dump of interfax.ru.
</td>
</tr>
<tr>
<td>
KP
</td>
<td>
<a name="load_taiga_kp"></a>
<code><a href="https://nbviewer.jupyter.org/github/natasha/corus/blob/master/docs.ipynb#load_taiga_kp">load_taiga_kp</a></code>
</td>
<td>
<code>news</code>
</td>
<td align="right">
45&nbsp;503
</td>
<td align="right">
61.79 Mb
</td>
<td>
Dump of kp.ru.
</td>
</tr>
<tr>
<td>
Lenta
</td>
<td>
<a name="load_taiga_lenta"></a>
<code><a href="https://nbviewer.jupyter.org/github/natasha/corus/blob/master/docs.ipynb#load_taiga_lenta">load_taiga_lenta</a></code>
</td>
<td>
<code>news</code>
</td>
<td align="right">
36&nbsp;446
</td>
<td align="right">
95.15 Mb
</td>
<td>
Dump of lenta.ru.
</td>
</tr>
<tr>
<td>
Taiga/N+1
</td>
<td>
<a name="load_taiga_nplus1"></a>
<code><a href="https://nbviewer.jupyter.org/github/natasha/corus/blob/master/docs.ipynb#load_taiga_nplus1">load_taiga_nplus1</a></code>
</td>
<td>
<code>news</code>
</td>
<td align="right">
7&nbsp;696
</td>
<td align="right">
24.96 Mb
</td>
<td>
Dump of nplus1.ru.
</td>
</tr>
<tr>
<td>
Magazines
</td>
<td>
<a name="load_taiga_magazines"></a>
<code><a href="https://nbviewer.jupyter.org/github/natasha/corus/blob/master/docs.ipynb#load_taiga_magazines">load_taiga_magazines</a></code>
</td>
<td>
</td>
<td align="right">
39&nbsp;890
</td>
<td align="right">
2.19 Gb
</td>
<td>
Dump of magazines.russ.ru
</td>
</tr>
<tr>
<td>
Subtitles
</td>
<td>
<a name="load_taiga_subtitles"></a>
<code><a href="https://nbviewer.jupyter.org/github/natasha/corus/blob/master/docs.ipynb#load_taiga_subtitles">load_taiga_subtitles</a></code>
</td>
<td>
</td>
<td align="right">
19&nbsp;011
</td>
<td align="right">
909.08 Mb
</td>
<td>
</td>
</tr>
<tr>
<td>
Social
</td>
<td>
<a name="load_taiga_social"></a>
<code><a href="https://nbviewer.jupyter.org/github/natasha/corus/blob/master/docs.ipynb#load_taiga_social">load_taiga_social</a></code>
</td>
<td>
<code>social</code>
</td>
<td align="right">
1&nbsp;876&nbsp;442
</td>
<td align="right">
648.18 Mb
</td>
<td>
</td>
</tr>
<tr>
<td>
Proza
</td>
<td>
<a name="load_taiga_proza"></a>
<code><a href="https://nbviewer.jupyter.org/github/natasha/corus/blob/master/docs.ipynb#load_taiga_proza">load_taiga_proza</a></code>
</td>
<td>
<code>lit</code>
</td>
<td align="right">
1&nbsp;732&nbsp;434
</td>
<td align="right">
38.25 Gb
</td>
<td>
Dump of proza.ru
</td>
</tr>
<tr>
<td>
Stihi
</td>
<td>
<a name="load_taiga_stihi"></a>
<code><a href="https://nbviewer.jupyter.org/github/natasha/corus/blob/master/docs.ipynb#load_taiga_stihi">load_taiga_stihi</a></code>
</td>
<td>
</td>
<td align="right">
9&nbsp;157&nbsp;686
</td>
<td align="right">
12.80 Gb
</td>
<td>
Dump of stihi.ru
</td>
</tr>
<tr>
<td>
<a href="https://github.com/buriy/russian-nlp-datasets/releases">Russian NLP Datasets</a>
</td>
<td colspan="5">
Several Russian news datasets from webhose.io, lenta.ru and other news sites.
</td>
</tr>
<tr>
<td>
Lenta
</td>
<td>
<a name="load_buriy_lenta"></a>
<code><a href="https://nbviewer.jupyter.org/github/natasha/corus/blob/master/docs.ipynb#load_buriy_lenta">load_buriy_lenta</a></code>
</td>
<td>
<code>news</code>
</td>
<td align="right">
699&nbsp;777
</td>
<td align="right">
1.57 Gb
</td>
<td>
Dump of lenta.ru.
</br>
</br>
<code>wget https://github.com/buriy/russian-nlp-datasets/releases/download/r4/lenta.tar.bz2</code>
</td>
</tr>
<tr>
<td>
News
</td>
<td>
<a name="load_buriy_news"></a>
<code><a href="https://nbviewer.jupyter.org/github/natasha/corus/blob/master/docs.ipynb#load_buriy_news">load_buriy_news</a></code>
</td>
<td>
<code>news</code>
</td>
<td align="right">
2&nbsp;154&nbsp;801
</td>
<td align="right">
6.84 Gb
</td>
<td>
Dump of top 40 news + 20 fashion news sites.
</br>
</br>
<code>wget https://github.com/buriy/russian-nlp-datasets/releases/download/r4/news-articles-2014.tar.bz2</code>
</br>
<code>wget https://github.com/buriy/russian-nlp-datasets/releases/download/r4/news-articles-2015-part1.tar.bz2</code>
</br>
<code>wget https://github.com/buriy/russian-nlp-datasets/releases/download/r4/news-articles-2015-part2.tar.bz2</code>
</td>
</tr>
<tr>
<td>
Webhose
</td>
<td>
<a name="load_buriy_webhose"></a>
<code><a href="https://nbviewer.jupyter.org/github/natasha/corus/blob/master/docs.ipynb#load_buriy_webhose">load_buriy_webhose</a></code>
</td>
<td>
<code>news</code>
</td>
<td align="right">
285&nbsp;965
</td>
<td align="right">
859.32 Mb
</td>
<td>
Dump from webhose.io, 300 sources for one month.
</br>
</br>
<code>wget https://github.com/buriy/russian-nlp-datasets/releases/download/r4/stress.tar.gz</code>
</td>
</tr>
<tr>
<td>
<a href="https://github.com/ods-ai-ml4sg/proj_news_viz">ODS #proj_news_viz</a>
</td>
<td colspan="5">
Several news sites scraped by members of #proj_news_viz ODS project.
</td>
</tr>
<tr>
<td>
Interfax
</td>
<td>
<a name="load_ods_interfax"></a>
<code><a href="https://nbviewer.jupyter.org/github/natasha/corus/blob/master/docs.ipynb#load_ods_interfax">load_ods_interfax</a></code>
</td>
<td>
<code>news</code>
</td>
<td align="right">
543&nbsp;962
</td>
<td align="right">
1.22 Gb
</td>
<td>
Dump of interfax.ru.
</br>
</br>
Manually download interfax_v1.csv.zip https://drive.google.com/file/d/1M7z0YoOgpm53IsJ3qOhT_nfiDnGUPeys/view
</td>
</tr>
<tr>
<td>
Gazeta
</td>
<td>
<a name="load_ods_gazeta"></a>
<code><a href="https://nbviewer.jupyter.org/github/natasha/corus/blob/master/docs.ipynb#load_ods_gazeta">load_ods_gazeta</a></code>
</td>
<td>
<code>news</code>
</td>
<td align="right">
865&nbsp;847
</td>
<td align="right">
1.63 Gb
</td>
<td>
Dump of gazeta.ru.
</br>
</br>
Manually download gazeta_v1.csv.zip from https://drive.google.com/file/d/18B8CvHgmwwyz9GWBZ0TS6dE_x6gYnWCb/view
</td>
</tr>
</table>
<!--- metas --->

## Licence

MIT

## Support

- Chat — https://telegram.me/natural_language_processing
- Issues — https://github.com/natasha/corus/issues


## Development

Tests:

```bash
make test
```

Add new source:
1. Implement `corus/sources/<source>.py`
2. Add import into `corus/sources/__init__.py`
3. Add meta into `corus/source/meta.py`
4. Add example into `docs.ipynb` (check meta table is correct)
5. Run tests (readme is updated)

Package:

```bash
make version
git push
git push --tags

make clean wheel upload
```
