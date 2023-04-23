# DataFrame

1. 读取csv

   ```python
   df = pd.read_csv(data_path)
   ```

2. 存储csv

   ```python
   df.to_csv(data_path)
   ```

3. 列拼接

   ```
   total_df = pd.concat([df1,df2],ignore_index=True)
   ```

4. shuffle

   ```
   from sklearn.utils import shuffle
   data_test = shuffle(data_test)
   ```

5. 选取列，(重命名,最小值，最大值)

   ```
   df = df[["ID","Sentence","label"]]
   df.columns = ["id","content",'label']
   t_start = cut_df["date"].min()
   ```

6. 按某一列值划分

   ```
   listType = total_df['id'].unique()
   for i,value in enumerate(listType):
       data_i = total_df[total_df['id'].isin([listType[i]])]
   ```

7. 对列进行统一操作

   ```
   def pseg_cut(text):
       seg = jieba.cut(str(text)) 
       return ' '.join(seg)
   df['seg_sentence'] = df['Sentence'].map(lambda x: pseg_cut(x))
   ```

8. 