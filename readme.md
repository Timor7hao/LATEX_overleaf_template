**（1）图占双栏**
```
%引用包  
\usepackage{stfloats}   
\usepackage{subfigure}         %子图  
	  
%样式写法
\begin{figure*}[ht]             %h:放在此处, p:放在本页, t:top, b:bottom  
	    \centering  
	    \subfigure[XXSubfig1CaptionXX   \label{fig:Subfig1}]  
	    {  
	        \begin{minipage}[b]{0.5\linewidth}  
	            \centering  
	            \includegraphics[width=1\linewidth]{picture/xxx.png}  
	        \end{minipage}%  
	    }%  
	    \subfigure[XXSubfig2CaptionXX   \label{fig:Subfig2}]  
	    {  
	        \begin{minipage}[b]{0.5\linewidth}  
	            \centering  
	            \includegraphics[width=1\linewidth]{picture/xxx.png}  
	        \end{minipage}%  
	    }%   
	    \centering  
	    \caption{XXTotalCaptionXX}\label{fig:FigTotal}   %caption标题,label引用  
\end{figure*}  

%文章中引用
\cite{fig:FigTotal}
```