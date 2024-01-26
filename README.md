# Causal Inference  
Causal inference by past data is important because we cannot always perform Randomized Controlled Tests (RCT). Some of the challenges are (1) confounders (i.e., variable that hasn't been controlled and has some causal effect; e.g., age), (2) selection bias (treatment group is not representative of population), and (3) counterfactuals (what would have been the case if this person did not receive treatment?; computed through matching or machine learning).  

Assumptions must be made because we want tailor prior data to become as representative as RCT as possible. We have to make assumptions because there are always some confounders that have some weird unitended effects on the outcome. 
* Causal Markov condition (Markov assumption): causal graph is a graph with directed edge that shows causation. The simplifed version is Directed Acyclic Graph (DAG; only goes one way)  
* Stable Unit Treatment Value Assumption (SUTVA): sample in the control group does not impact sample in the treatment group to prevent interaction effects  
* Ignorability: there is no additional unknown confounder  

Measuring Average Treatment Effect (ATE) is useful to make decisions on a population, and Conditional Average Treatment Effect (CATE) is useful to make decision on subsets of the population. When CATE is different, there is treatment heterogeneity. 

## Difference-in-Difference (DiD)  
Instead of simply calculating the difference in averages (given that it is important to account for possible different starting points, like the treatment group already has higher number of hateful content), DiD helps identify the treatment effect as thedifference in changes over time across groups.  

A=control (cluster 1 control), B=treatment (cluster 1)  
1=pre-treatment (pre-disruption), 2=post-treatment (post-disruption)  

δ<sub>DD</sub> = (Ȳ<sub>B,2</sub> - Ȳ<sub>A,2</sub>)-(Ȳ<sub>B,1</sub> - Ȳ<sub>A,1</sub>) = Effect of treatment on outcome  
(Ȳ<sub>B,2</sub> - Ȳ<sub>A,2</sub>)=difference across types "after" treatment  
(Ȳ<sub>B,1</sub> - Ȳ<sub>A,1</sub>)=difference across types "before" treatment  

δ<sub>DD</sub> = (Ȳ<sub>B,2</sub> - Ȳ<sub>B,1</sub>)-(Ȳ<sub>A,2</sub> - Ȳ<sub>A,1</sub>) = Average Treatment Effect  
(Ȳ<sub>B,2</sub> - Ȳ<sub>B,1</sub>)=treatment impact on "treated"    
(Ȳ<sub>A,2</sub> - Ȳ<sub>A,1</sub>)=treatment impact on "control"    

OLS (Ordinary Least Square) estimate of DiD is common method used to estimate the treatment effect in DiD analysis.
