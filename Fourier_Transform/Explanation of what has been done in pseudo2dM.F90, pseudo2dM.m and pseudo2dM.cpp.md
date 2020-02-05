The central idea is to calculate the complex fourier form, then use inverse DFT to have real fields.

###The fortran version is using the (-N/2+1,N/2) version of DFT.

\[summ=\sum_{p=-N/2+1}^{N/2} \sum_{l=-N/2+1}^{N/2}  e^{-2(\frac{\kappa^2 l^2}{r_1^2}+\frac{\lambda^2 p^2}{r_2^2})}
\]

\[c=\sqrt{\frac{1}{\delta k (summ-1)}}
\]

The real and imag parts are calculated respectively:

For $p=-N/2-1,N/2$
   For $l=0,N/2$
\begin{align}
e(l,p)&=e^{-(a_{11}\kappa^2 l^2+2a_{12}\kappa\lambda lp+a_{22}\lambda^2p^2)}\\
real(l,p)&=e(l,p)cos(\phi(l,p))\sqrt{\delta k}c=e(l,p)cos(\phi(l,p))/\sqrt{summ-1}\\
imag(l,p)&=e(l,p)sin(\phi(l,p))\sqrt{\delta k}c=e(l,p)sin(\phi(l,p))/\sqrt{summ-1}
\end{align}

assign them to complex variable:

For $p=0,N/2-1$
\begin{align}
x(:,p)=real(:,p)+imag(:,p)i
\end{align}
For p=$N/2,N-1$
\begin{align}
x(:,p)=real(:,p-N)+imag(:,p-N)i
\end{align}

So here $x$ is $0,N-1$ indexed, while real and imag are $-N/2+1,N/2$ indexed, eventually $y$, the real output is $0,N-1$ indexed.

###The matlab version 

\[summ=\sum_{p=-N/2+1}^{N/2} \sum_{l=-N/2+1}^{N/2} e^{-2(\frac{\kappa^2 l^2}{r_1^2}+\frac{\lambda^2 p^2}{r_2^2})}
\]

The complex variable is created:

For $l=0,N/2-1;-N/2,-1$
   For $p=0,N-1$
\[A(l,p)=e^{-((a_{11}\kappa^2 l^2+2a_{12}\kappa\lambda lp+a_{22}\lambda^2p^2)}(cos(\phi(l,p))+isin(\phi(l,p)))/\sqrt{summ-1}\]

###The c version

\[summ=\sum_{p=-N/2+1}^{N/2} \sum_{l=-N/2+1}^{N/2} e^{-2(\frac{\kappa^2 l^2}{r_1^2}+\frac{\lambda^2 p^2}{r_2^2})}
\]

If thes summ is changed through 0 to N-1, this value is increased which leads to different magnitude of correlation matrix.

The real and imag parts are calculated respectively:

For $l=0,N-1$
   For $p=0,N/2+1$
   \begin{align}
      e(l,p)&=e^{-(a_{11}\kappa^2 l^2+2a_{12}\kappa\lambda lp+a_{22}\lambda^2p^2)}\\
      real(l,p)&=e(l,p)cos(\phi(l,p))\sqrt{\delta k}c=e(l,p)cos(\phi(l,p))/\sqrt{summ-1}\\
      imag(l,p)&=e(l,p)sin(\phi(l,p))\sqrt{\delta k}c=e(l,p)sin(\phi(l,p))/\sqrt{summ-1}
   \end{align}

then $x$ is a complex varaible of dimension $N*(N/2+1)$
For $l=0,N/2-1$
\begin{align}
x(l,:)=real(l,:)+imag(l,:)i
\end{align}
For $l=N/2,N-1$
\begin{align}
x(l,:)=real(l,:)+imag(l,:)i
\end{align}