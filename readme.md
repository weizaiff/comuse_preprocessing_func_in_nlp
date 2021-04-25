# 常用func
## 1.词还原

lem = nltk.stem.wordnet.WordNetLemmatizer()
text = lem.lemmatize(text)

## 2.word cloud

mostcommon = FreqDist(allwords).most_common(100)#来自文本中出现频率最高的100个词
wordcloud = WordCloud(width=1600, height=800, background_color='white', stopwords=STOPWORDS).generate(str(mostcommon))
fig = plt.figure(figsize=(30,10), facecolor='white')
plt.imshow(wordcloud, interpolation="bilinear")
plt.axis('off')
plt.title('Top 100 Most Common Words in cleaned_label', fontsize=50)
plt.tight_layout(pad=0)
plt.show()

## 3.找到文件夹下所有的文件

for dirname, _, filenames in os.walk('/kaggle/input'):
    for filename in filenames:
        print(os.path.join(dirname, filename))
        break

## 4.df 中apply function 对其中的单列起作用，当使用groupby之后，apply可以对一个group的DF结构操作。


## 5.判定Dataframe中找到lie值为Nan的列:
labelext_res_df.loc[pd.isna(labelext_res_df['human_label'])]

## 6.找到字符串中所有所需的字符串

import re
[m.start() for m in re.finditer('test', 'test test test test')]