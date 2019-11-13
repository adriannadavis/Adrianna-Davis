# README for pr2 R database package
After installing and loading the pr2database from the GitHub website, changes were made to the "Working with the database" module; specifically, changes were made to the selection of specific taxon. Directions on installing the pr2database can be found here: https://github.com/pr2database/pr2database/wiki/PR2-R-database-package. 

 Selecting sequences from a specific taxon:

   Select all the available sequences for the Suessiales in replacement of Mamiellophyceae Ostreococcus

    # Filter only the sequences for which the column genus contains Suessiales
    pr2_sues <- pr2 %>% dplyr::filter(genus == "Suessiales")

    # Select only the columns of interest
    pr2_sues <- pr2_sues %>% dplyr::select( genbank_accession, species, 
                                              pr2_sample_type, gb_strain, gb_clone, 
                                              pr2_latitude, pr2_longitude, 
                                              sequence_length, sequence  )
  
    pr2_sues
  
  Make an additional instruction to export Suessiales data 
    # Export data to the file   
    write.table(pr2_sues, "~/analysis/pr2_sues.tsv", sep="\t", quote=F, col.names=NA)
  
  Continue with the provided instructions with the subsitution of Ostreococcus with Suessiale
