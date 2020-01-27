
# Ruin Problems

## Survival Probability of an Economic Agent under Production Uncertainty  

One problem in mathematical economics considers the probability of survival of an economic agent whose stock $X_n$ evolves according 
to the Markov model $X_{n+1}=\epsilon_{n+1} (X_n  – c)$. Here $c$ is the constant level of consumption needed for the agent's 
survival, and $\epsilon_n$ are i.i.d. multiplicative shocks for production in the next period. One is interested in the probability of 
survival, namely, 

\begin{equation}   
\epsilon(x)=(X_n>c \,for\, all\, n│X_0=x), \, x>c. 
\end{equation}
                                                                                                                                                                              
Numerous prominent economists have considered this problem[<sup>1</sup>](#M1991) [<sup>2</sup>](#M1992) [<sup>3</sup>](#M1993). No analytical solutions are available in the non-trivial case 
$E (log \epsilon_n) > 0$, especially when $0 < \epsilon(x) < 1$ for all $x>c$. One can show that $\epsilon(x)$ is determined by the 
distribution function of a random variable, $Z=\sum_{n=1}^{\infty} (\epsilon_1 \epsilon_2 \cdots \epsilon_n)^{-1}$, which is obtained 
by successive iteration. However, its distribution seems intractable. I have developed a method of exactly computing the moments of 
$Z$ using the moments of the shock, $\epsilon_n$. This recursive method automatically determines when the moment of $Z$ first becomes 
infinite. Based on this and a new method using a system of Chebyshev-type inequalities with different moments for different intervals 
of $x$-values, each moment provides the best estimate for the corresponding interval. The resulting lower bounds are shown, by 
extensive simulations, to provide good estimates of $\epsilon(x)$. This novel method also provides good estimates of $\epsilon_n (x)$,
the probability of survival of an economic agent up to the finite time $n$ with an initial stock $x>c$. In the same fashion, 
$\epsilon_n (x)$ is determined by the distribution function of a random variable $Z_n=\sum_{j=1}^n (\epsilon_1 \epsilon_2 \cdots \epsilon_j)^{-1}$[<sup>4</sup>](#R2015) [<sup>5</sup>](#K2015).  

* The article can be found here.[<sup>4</sup>](#R2015)  
        
## Rate of Convergence to Equilibrium 

A different topic is the estimation of the ruin probability in insurance in the general renewal model, especially under heavy-tailed 
or sub-exponential claim size distributions. The literature here is vast and a great deal of activity is still going on in this area.  
My focus is the estimation of finite time ruin probabilities. Particularly very little is known for the heavy-tailed case. Apart 
from more conventional treatments in the finance/insurance literature, I have also been exploring the rather purely formal 
mathematical connection between this problem and the problem of speed of convergence to steady state in the general Markov model known 
as the Lindley-Spitzer process. The convergence rate is exponential in the case of light-tailed distributions. In the heavy-tailed 
case the rate depends on the number of moments that are finite. If only a finite number of moments exist, then the rate is 
polynomial. This leads to the possibility of estimating the ruin probability in insurance in finite time. Extensive empirical 
studies showed the convergence rates for the both as the theory predicts [<sup>6</sup>](#R2015-1) [<sup>7</sup>](#R2010) [<sup>8</sup>](#R2010-1).  



---



<span id="M1991">[1] M. Majumdar and R. Radner. Linear models of survival under production uncertainty. <i>Economic Theory</i>, 1:13-30, 1991.</span>

<span id="M1992">[2] M. Majumdar and R. Radner. Survival under production uncertainty: in “Equilibrium and Dynamics” (M. Majumdar, Ed.). pages 179-200,1992.</span>

<span id="M1993">[3] T. Mitra and S. Roy. On some aspects of survival under production uncertainty. <i>Economic Theory</i>, 3(3):397-411, 1993.</span>

<span id="R2015">[4] R. Bhattacharya, H. Kim, and M. Majumdar. Sustainability in the stochastic Ramsey model. <i>Journal of Quantitative Economics</i>, 2015. DOI: 10.1007/s40953-015-0020-5.</span> <a href="https://www.researchgate.net/publication/284579591_Sustainability_in_the_Stochastic_Ramsey_Model">article</a> 
    
<span id="K2015">[5] H. Kim. <i>Probabilities of Ruin in Economics and Insurance under Light- and Heavy-tailed Distributions.</i> PhD thesis, GIDP in Statistics, University of Arizona, USA, 2015.</span>

<span id="R2015-1">[6] R. Bhattacharya and M. Majumdar. Ruin probabilities in models of resource management and insurance: A synthesis. <i>International Journal of Economic Theory</i>, 11(1):59-74, 2015.</span>

<span id="R2010">[7] R. Bhattacharya, M. Majumdar, and N. Hashimazade. Limit theorems for monotone Markov process. <i>Sankhya A</i>, 72(1):170-190, 2010.</span>

<span id="R2010-1">[8] R. Bhattacharya and R. R. Rao. <i>Normal Approximation and Asymptotic Expansions</i>, volume 64. SIAM, 2010.</span>








