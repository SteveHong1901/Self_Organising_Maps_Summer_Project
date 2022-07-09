# NCSOM-MAPS-Research

# This project is still happening. Materials have not been revised

Pseudocode for NCSOM Model
Variables
mj: weight vectors,  j: the number of neurons
xi: input vectors,  i: the number of input vectors
ci: arg min d(x, m)
h: neighbourhood function value
d: number of features, p: number of numeric features, k: kth categorical features

Pseudocode
Step 1: Initialise the weights  and normalise input data
#Random generation of the weights:
#We need to randomise the numerical part and the categorical part, then merge them

define j,p,k
define m = [ ]

#Numerical
for each neuron in range j:
m.append(np.random.rand(p,1))

#Categorical
#extract the possible categories for each variable (using unique() function on each variable)
#a library can be found to randomise the outcode of each variable. If there is none available,
#one way could be to make a rand_cat() function that randomises interger (0, number of categories) then match
#the returned index to the list of unique possibilities from above.

for mj in m:
	cat = rand(k) for k in range of (d-p)
	append cat to each neuron


#Step 2: Calculate distances and BMU for each observation
#Define a function to calculate the distance between x and m by using index
Def distance(data, neuron, no_of_numvar, no_of_var ):
	num_dist = (data[0, no_of_numvar] – neuron[0, no_of_numvar])2            
	cat_dist = 0
for counter in range (no_of_numvar + 1, no_of_var):
		if data[no_of_numvar+1] == neuron [no_of_var]:
			cat_dist += 0
		else:
			cat_dist += 1
	return num_dist + cat_dist

#for each xi, compute d(xi,mj) for all values of m. Create tracker variables to track the minimum values of distance and the according BMU for each value of xi. Add the index of it to a list.
c_list = [ ]
min_dist = 0
for xi in x:
	dist = distance(xi, mj) for mj  in m
	if dist < min_dist:
		c_list . append (index(mj))
	min_dist = min(dist, min_dist)


#Step 3: Update the weights using all data (Batch Algorithm)
#Compute a list of neighourhood function values for each value of m using the list of c

Summary of the Update:
1)Given a list of i neurons positioned on a 2D grid and a list of winning neurons
2)For numerical: Find the list of neighbourhood function values (hi) using h = exp(-〖(sqrt(m,c))〗^2/(2σ^2 (t))). The distance defines the amount of update is that between each neuron being updated and the list of winning neuron: the further they are the smaller the update. If the winning neuron is the neuron itself, the weights stay the same (could be verified using the formula). The σ^2 (t) component shrinks over time. 
3) For categorical: With the same list of winning neurons and h, the updates are however defined differently. The relative frequency of each of the possibilities of each categorical variable are calculated. Then the one that has a larger relative frequency than the rest would be chosen as the update. 
4)Merge the numerical and categorical weight vectors together. 

#Numerical
for each neuron on the grid:

	find its distances (h)  on the grid from the winning neurons from the list, then divide by
	a function of time/number of iteration. The distance is calculated in Cartesian form. Store
	these values in a list.

	denominator =  the sum of these values of h
	numerator_num = the sum of these values multiplied with the list of input vectors
	new_weight_num  = numerator/denominator 


#Categorical

def f_value(name_of_variable, name_of_outcome):

filter out the winning neurons (referenced from above) whose 
name_of_variable variable = name_of_outcome. Make them a list
	
find the distances on the grid between these winning neurons and the neuron 
to be updated. Store these distance values in list_1
		
find the distances on the grid between all winning neurons and the neuron 
to be updated. Store these distance values in list_2

numerator_cat = sum of  the values of h from list_1
denominator = sum of all the values of h from list_2

return numerator_cat/denominator

for each neuron on the grid:
for each categorical variable (indices from p+1 to d):
f_list = [ ] 
f = f_value(name_of_variable, name_of_outcome) and flist.append(f) for each of its 
possible outcome

for each of the f values from f_list:
	if it is bigger than sum of the rest:
		update the weight to the name_of_outcome
	else:
		keep the current weight
	

#Categorical
#For the numerator, we need to find the new list of input data (conditioning on the category), thus #compute a new list of BMU and then compute h

def h_cond(data, category, no_of_numvar, no_of_var):
	#Filtering out data that includes the category
	new_x = [ ] 
for xi in data:
new_x.append(xi) if category is in xi

	#Find the BMU
	bmu_list_cond = [ ]
min_dist = 0
for xi in new_x:
		dist = distance_cat(xi, mj) for mj  in m
		bmu_list_cond . append (mj) if dist < min_dist else pass
		min_dist = min(dist, min_dist)

	#Compute the list of h
	for mj in m:
for ci in bum_list_cond:
h = exp(-〖distance_cat(m,c,p)〗^2/(2σ^2 (t)))
return h
	
#Update the category section	
for mj in m:
for ci in c:
		h = exp(-〖distance_cat(m_j,c_i,p)〗^2/(2σ^2 (t))) 
		denom += h

num = h_cond(x,unique_list,p,d)

m_update_cat = num

	


	



