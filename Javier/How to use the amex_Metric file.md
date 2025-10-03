#### 2\. Import and Use It in Your Notebook

Now, in your Jupyter Notebook, you can delete the original large function block. At the top of your notebook, with your other imports, add this line:

```python
from amex_metric import amex_metric
```

You can now use the function in your cross-validation loop just like you used `roc_auc_score`, but remember it requires DataFrames as input.

```python
# Inside your CV loop
y_val_df = y_val.to_frame(name='target')
preds_df = pd.DataFrame({'prediction': preds}, index=y_val.index)

score = amex_metric(y_val_df, preds_df)
print(f"Fold {fold+1} Amex Metric: {score:.4f}")
```