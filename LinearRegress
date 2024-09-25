p : 0 : "Path/To/Your/Data"; p : ((_ 0.5*#p),2)#p
meanX : (+/ {. (p@x)@1}' !(#p))* %(#p); meanY : (+/ {. (p@x)@0}' !(#p))* %(#p) /mean x and mean y
Var : (+/ {((. (p@x)@1)-meanX)^2}' !(#p))* %((#p)-1); Cov : (+/ {((. (p@x)@0) - meanY)*((. (p@x)@1) - meanX)}' !(#p))* %((#p)-1)
beta1 : Cov%Var; beta0 : meanY - (beta1*meanX)
y : {. (p@x)@0}' !#p; xi : {. (p@x)@1}' !#p; yhat : {beta0 + (beta1*(xi@x))}'!#xi; u : y - yhat
sigma2 : (+/ _sqr u) * % ((#u) -  2); sse : +/ _sqr (yhat - meanY); ssr : +/ _sqr u; sst : +/ _sqr (y - meanY); r2 : sse%sst
beta0, beta1, sigma2, r2
