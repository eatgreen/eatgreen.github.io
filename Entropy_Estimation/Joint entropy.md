Suppose we have two parameters $\theta$ and $\alpha$, every parameter has realizations
for $\theta$, its entropy is
\[H(\theta)=-\sum_{\theta} p_{\theta}log(p_{\theta})=-\big(p^1_{\theta}log(p^1_{\theta})+p^2_{\theta}log(p^2*{\theta})+p^3_{\theta}log(p^3_{\theta})\big)
\]
likewise for $\alpha$
\[H(\alpha)=-\sum_{\alpha} p_{\alpha}log(p_{\alpha})=-\big(p^1_{\alpha}log(p^1_{\alpha})+p^2_{\alpha}log(p^2_{\alpha})+p^3_{\alpha}log(p^3_{\alpha})\big)
\]
So what is originally maxmized is
\[argmax\,\, H = H(\theta) + H(\alpha)
\]
For joint distrubution of independent variables
\[p_{\theta\alpha}=p_{\theta}p_{\alpha}\]
The joint entropy is 
\[H(\theta,\alpha)=-\sum_{\theta}\sum_{\alpha}p_{\theta\alpha} log(p_{\theta\alpha})\]
This should up to
\begin{align}
H(\theta,\alpha)=-\big(& p^{11}_{\theta\alpha} log(p^{11}_{\theta\alpha}) + p^{12}_{\theta\alpha} log(p^{12}_{\theta\alpha}) + p^{13}_{\theta\alpha} log(p^{13}_{\theta\alpha}) \\
&+ p^{21}_{\theta\alpha} log(p^{21}_{\theta\alpha}) + p^{22}_{\theta\alpha} log(p^{22}_{\theta\alpha}) + p^{23}_{\theta\alpha} log(p^{23}_{\theta\alpha}) \\
&+ p^{31}_{\theta\alpha} log(p^{31}_{\theta\alpha}) + p^{32}_{\theta\alpha} log(p^{32}_{\theta\alpha}) + p^{33}_{\theta\alpha} log(p^{33}_{\theta\alpha}) \big)
\end{align}
If we know $p_{\theta}=(p^1_{\theta},p^2_{\theta},p^3_{\theta})$ which suffices $\sum p_{\theta}=1$, 
\[p^{11}_{\theta\alpha}=p^1_{\theta}p^1_{\alpha}.
\]
For the current code, we can keep the control vector p_v containing 95*3 members, but entropy has to be recomputed by above formula.