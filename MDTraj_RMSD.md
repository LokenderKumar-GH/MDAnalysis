%matplotlib inline 
import mdtraj as md #import mdtraj as md
import matplotlib.pyplot as plt 

traj = md.load('md_0_1_noPBC.xtc', top= 'md_0_1.gro')
traj

traj.center_coordinates()#precenter the trajectory 

rmsds = md.rmsd(traj, traj, 0) #assign trajectory to a variable rmsds


plt.figure(figsize=(14, 3))#set the size of plot (x and y)
plt.plot(rmsds, color = 'green', linewidth=1)#plot the rmsd of the trajectory
plt.xlabel('Time', fontsize = 20)#add label to x axis and set the font size 
plt.ylabel('RMSD(nm)',fontsize = 20)#add label to y axis and set the font size
plt.ylim(6.44, 6.55)#set the limit of y-axix 
plt.xlim(0, 10000)#set the limit on the x-axis
plt.title('RMSD', fontsize = 20)# add title and also the font size
plt.tight_layout() #get rid of extra white space in the figure
plt.show()#show the final plot with all the settings

