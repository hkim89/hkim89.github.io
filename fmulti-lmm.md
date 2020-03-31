
# Multivariate Linear Mixed Models (MLMM)

## Flexible Algorithm by Multivariate Linear Mixed Model 
     
A problem that arises in plant breeding is to understand individual genetic regions contributing to trait variation across 
geographic space.  The data are high-dimensional and structured by a host of growing season phenotypes of plants, for instance, 
switchgrass, screened for a series of high-throughput physiological measurements in 10 different latitudes for multiple years [<sup>1</sup>](#gxe). 

One is interested in determining the genomic regions underlying upland/lowland ecotype divergence and adaptation for switchgrass by 
assessing gene by environment interactions (GxE) across space and climate variation.  A high-dimensional multivariate linear mixed 
model assuming phenotypes are correlated due to genetic similarity, measured by genome-wide markers, and environmental similarity, by 
climatic or edaphic information, is built as follows: 

\begin{equation}     
                     Y=XBZ'+R+E, 
\end{equation}                     
              
or implicitly             
\begin{equation}                   
                    Y^v\sim MVN((Z\otimes X) B^v,\tau^2 K_C\otimes K_G+\Sigma\otimes I_n),
\end{equation} 
                     
where the superscript $v$ means the vectorized form of a matrix, $Y_{n\times m}$, $X_{n\times p}$, $Z_{m\times q}$ are $n$ phenotypic 
trait values over $m$ environments, $p$ genotypes of genotype probabilities (with covariates) with the intercept for a candidate 
marker,  $q$ phenotypic low-dimensional covariates, respectively.  $R$, $E$  are GxE random effects including high-dimensional column 
covariates, model or residual errors, respectively.  

Incorporating genetic background information, kinship matrix ($K_G$) with climate 
information over multiple environments ($K_C$) generates an infinitesimal random GxE effects.  Meanwhile, a functional phenotypic 
trend along the environments, interactions between an individual genetic marker and multiple environments can be accounted using the 
fixed column covariates ($Z$).  This novelty can significantly reduce the size of parameters to estimate and gives yet flexibility 
applicable to a wider variety of data, such as MLMM for multiple traits, time-valued phenotypic curves, or accelerometer data, etc. 

The algorithm is developed in Julia using an Expectation Conditional Maximization (ECM) [<sup>4</sup>](#ecm) with a Speed Restarting Nesterov’s Accelerated 
Gradient method [<sup>5</sup>](#nest).  Extensive simulations show that the results are relatively insensitive to different $K_C$’s; $K_C=I$ can be 
used for fast computation to have a rough idea on initial analysis.  Based on on-going analyses of the switchgrass data containing 4 
traits measured in 10 sites on the latitude by 3 years ($m =30$ per trait), the results depending on $K_C$’s are expected to show 
discrepancy for higher dimensional environments ($m>30$).  As expected, the low fixed column covariates ($Z$) show better performance 
than the conventional model, i.e. $Z=I$, in power analysis.  

Furthermore, the analyses of fitness in Arabidopsis thaliana with climate 
information in 2 sites by 3 years ($m = 6$) [<sup>6</sup>](#agren) and weekly weight growth rate in island mice from 1 to 16 weeks of age ($m =16$) [<sup>7</sup>](#goughF2)
using the model developed are not only consistent with those published in the papers but detected more QTL than those.  In addition to 
collaborating with Dr. Thomas Jeunger in Integrated Biology department at the University of Texas at Austin on the switchgrass data, I 
am working on the data analysis of Outbred Diversity/Heterogeneous Stock (DO/HS) mouse data on travel distance measured in each 
miniute with Dr. Vivek Philip at Jackson laboratory using the model developed with some tweaks.\\
                                                

* [Manuscript](https://www.biorxiv.org/content/10.1101/2020.03.27.012690v1) is available in BioRxiv.

* Presentation slides can be found [here.](p30_gxe.pdf)

* Github repository : [fMulti-LMM](https://github.com/hkim89/fMulti-LMM)                                            
                                                
                                                






---

<span id="gxe">[1] D. B. Lowry, J. T. Lovell, L. Zhang, J. Bonnette, P. A. Fay, R. B. Mitchell, J. Lloyd-Reilley, A. R. Boe, Y. Wu, F. M. Rouquette Jr, R. L. Wynia, X. Weng, K. D. Behrman, A. Healey, K. Barry, A. Lipzen, D. Bauer, A. Sharma, J. Jenkins, J. Schmutz, F. B. Fritschi, and T. E. Juenger. QTL x environment interactions underlie adaptive divergence in switchgrass across a large latitudinal gradient. <i>PNAS</i>, 116(26):12933-12941, 2019.</span>

<span id="gemma">[2] X. Zhou and M. Stephens. Efficient multivariate linear mixed model algorithms for genome-wide association studies. <i>Nature Methods</i>, 11(4):407-409, 2014.</span>

<span id="fast">[3] C. Lippert, J. Listgarten, Y. Liu, C. M. Kadie, R. I. Davidson, and D. Heckerman. FaST linear mixed models for genome-wide association studies. <i>Nature Methods</i>, 8(10):833-835, 2011.</span>

<span id="ecm">[4] X. L. Meng and D. B. Rubin. Maximum likelihood estimation via the ECM algorithm: A general framework. <i>Biometrica</i>, 80(2):267-278, 1993.</span>

<span id="nest">[5] W. Su, S. Boyd and E. Candès. A differential equation for modeling Nesterov’s accelerated gradient method: Theory and Insights. <i>In Advances in Neural Information Processing Systems</i>, pages 2510-2518, 2014.</span>

<span id="agren">[6] J. Ågren, C. G. Oakley, J. K. McKay, J. T. Lovell, and D. W. Schemske. Genetic mapping of adaptation          
         reveals fitness tradeoffs in Arabidopsis thaliana. <i>PNAS</i>, 110(52): 21077-21082, 2013.</span>

<span id="goughF2">[7] M. M. Gray, M. D. Parmenter, C. A. Hogan, I. Ford, R. J. Cuthbert, P. G. Ryan, K. Broman, and B. A.     
        Payseur. Genetics of rapid and extreme size evolution in island mice. <i>Genetics</i>, 201(1):213-228, 2015.</span>


