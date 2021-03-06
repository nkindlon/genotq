# KANBAN

## GOALS

* Support queires
    * Get all variants where at least N of affected individuals are
      heterozygous and no more than M of the unaffected are heterozygous
        * Get a count of how often each variant meets a condition in a subset
        * Conditional subtract
            * Condition
            * Subtract
    * Get all varaints where the allele frequency is at least N 
        * Summation
    * Get variants that meet specific genotypes

### Urgent
* Test the tradeoff between compression ratio and query for WAH using 8, 16, 32, and 64 bit words.


### High Value

* Needed operations:
    * eq (equal) operator. for example, sample Joe is HET (1) or samples 1-M are HOM_REF (0)
    * ne (not equal) operator. for example, sample Joe is not HET (0,2, or 3) or samples 1-M are not HOM_REF (1,2,3)


* Get a 1KG data set to validate results
    * Download 1KG VCF
    * Convert to:
        * sorted ind.txt
        * ind.txt
        * ind.txt.bgz/tabix
        * ind.wah
        * ped
        * bed
        * vcf
        * bcf

* Query time tests
    * WAH
    * RLE
    * plain text
    * grabix
    * uncompressed binary
    * vcf
    * bcf


* Funcitonal Tests
    * Convert to WAH
    * RLE
    * plain text
    * grabix
    * uncompressed binary
    * vcf
    * bcf

* invert major from (records -> fields/ fiels -> records)

### Improvements

* generalized to 32 or 64 bit 
    * WAH
    * uncompressed binary

### Brain Storm

* Create an N-bit WAH compression scheme
* Create a compression scheme that enables efficient (parallel?) sweeps
    * This may be a very good GPU target

## QUEUE

### Ryan
* plt-to-vcf
* count and sum based on compressed in-place 

## IN PROGRESS

### Aaron
#### Develop
* grabix
    * right now all of the genotq grabix code is in src/c/gt_records_grabix.cpp, which looks a lot like the gt_records_plt.
      I have added a few functions to grabix (included in the latest github pull request) that allow the file to be opend,
      lines extracted as **char, and then closed.  The goal here is to bring grabix into genotq such that it has the same 
      set of functions that ubin, wah, plt, etc. have.  Once grabix is all C (not C++), the query functions should be very similar
      to plt 
* ubin >,<,>=,<= than query

#### Document
#### Verify

### Ryan

#### Develop
* count gt
    * ubin

#### Document


#### Verify

## DONE
* file conversion
    * plt to ubin
    * ubin to wah
    * ubin to wahbm
    * vcf to plt
* file print
    * plt
    * ubin packed int
    * ubin plt
    * wahbm plt
    * wah plt
* wah >,<,>=,<= than query
* plt >,<,>=,<= than query
* 16-bit word wah file conversion
* do in place OR
* compressed in-place OR and AND
    * compressed in-place wah to ints
* count gt
    * wah
    * plt
    * in place
    * compressed in place
* invert plt
