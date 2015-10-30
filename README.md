#PLEASE NOTE:  THIS GITHUB PAGE IS A WORK IN PROGRESS!  
I have tested these programs on my local machine but I am currently working on uploading files.
I will remove this warning when I have finished.

# hPSMC
Tools for F1 hybrid PSMC (hPSMC) divergence time inference from whole genomes


1) Create an hPSMC .psmcfa input file from two samples 

	haploidize each bam file to a fasta
	
	combine fasta sequences from two individuals into a single .psmcfa file.
	
	
2) run psmc using the hPSMC.psmcfa

	We ran PSMC under default settings. See https://github.com/lh3/psmc
	
	psmc -N25 -t15 -r5 -p "4+25*2+4+6" -o hPSMC.psmc hPSMC.psmcfa
	

3) Visualize hPSMC.psmc and estimate pre-diverence population size.

	Standard PSMC method.
	
		psmc_directory/utils/psmc_plot.pl hPSMC hPSMC.psmc
		
	Alternative script included here. The -s -g and -m flags show their default values.
	
		python hPSMC/PSMC_emit_last_iteration_coord.py -s10 -g25 -m0.000000001 hPSMC.psmc
		
	Once we have plotted the psmc result using one of the two above methods estimate the pre-divergence population size which will be input for step 4.
		

4) Run simulations of divergence without post-divergence migration to compare to the hPSMC plot

	In order to interpret

5) Plot simulations with the orignal data to show the divergence between samples.

