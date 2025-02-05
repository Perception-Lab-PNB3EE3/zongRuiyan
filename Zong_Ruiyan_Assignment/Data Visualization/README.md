
# First visualize the whole dataset
y_values = df["y"].values
x_values = df["x"].values

conditions = df["condition"].values
unique_conditions = np.unique(conditions)

COLORS = ["black", "#D95F02", "#7570B3", "#91BA88"]

fig, ax = plt.subplots(figsize=(8,8))
for condition, color in zip(unique_conditions, COLORS):
    idxs = np.where(condition == conditions)
    # No legend will be generated if we don't pass label=species
    ax.scatter(
        x_values[idxs], y_values[idxs], label=condition,
        s=50, color=color, alpha=0.7
    )
    
ax.legend()
plt.show()


# Then I visualize the sumamry statistics for each condition
## Plot 1
# width of the bars
barWidth = 0.1

condition1 = stats.loc['condition_1'].values
condition2 = stats.loc['condition_2'].values
condition3 = stats.loc['condition_3'].values
condition4 = stats.loc['condition_4'].values
 
# The x position of bars
r1 = np.arange(len(condition1))
r2 = [x + barWidth for x in r1]
r3 = [x + barWidth for x in r2]
r4 = [x + barWidth for x in r3]
 
# Create blue bars
plt.bar(r1, condition1, width = barWidth, color = '#1B9E77', edgecolor = 'black', capsize=7, label='condition1')
plt.bar(r2, condition2, width = barWidth, color = '#D95F02', edgecolor = 'black', capsize=7, label='condition2')
plt.bar(r3, condition3, width = barWidth, color = '#7570B3', edgecolor = 'black', capsize=7, label='condition3')
plt.bar(r4, condition4, width = barWidth, color = '#91BA88', edgecolor = 'black', capsize=7, label='condition4')

 
# general layout
plt.xticks([r + barWidth for r in range(len(condition1))], ['x mean', 'x std', 'y mean', 'y std'])
plt.ylabel('height')
plt.legend()
 
# Show graphic
plt.show()
condition1

## Plot 2
barWidth = 0.3
 
# Choose the height of the x_value bars
bars1 = stats['x','mean']
 
# Choose the height of the y_value bars
bars2 = stats['y','mean']
 
# Choose the height of the error bars (bars1)
yer1 = stats['x','std']
 
# Choose the height of the error bars (bars2)
yer2 = stats['y','std']
 
# The x position of bars
r1 = np.arange(len(bars1))
r2 = [x + barWidth for x in r1]
 
# Create blue bars
plt.bar(r1, bars1, width = barWidth, color = 'blue', edgecolor = 'black', yerr=yer1, capsize=7, label='x_value')
 
# Create cyan bars
plt.bar(r2, bars2, width = barWidth, color = 'cyan', edgecolor = 'black', yerr=yer2, capsize=7, label='y_value')
 
# general layout
plt.xticks([r + barWidth for r in range(len(bars1))], ['cond_1', 'cond_2', 'cond_3', 'cond_4'])
plt.ylabel('mean')
plt.legend()
 
# Show graphic
plt.show()