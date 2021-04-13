**（1）图占双栏**
```
%引用包  
\usepackage{stfloats}   
\usepackage{subfigure}         %子图  
	  
%样式写法
\begin{figure*}[hb]             %h:放在此处, p:放在本页, t:top, b:bottom  
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
Figure~\ref{fig:FigTotal}
```
![image](https://user-images.githubusercontent.com/38340783/114511647-c45fa100-9c6a-11eb-9503-8a007c6859df.png)

**（2）图占单栏**
```
%引用包  
\usepackage{stfloats}   
\usepackage{subfigure}              %子图  

%样式写法
\begin{figure}[!t]                  %t:top, b:bottom  
    \centering  
    \includegraphics[width=0.9\columnwidth]{picture/xxx.png}  
    \caption{XXFigCaptionXX}  
	\label{fig:Fig}            %caption标题,label引用  
\end{figure} 

%文章中引用
Figure~\ref{fig:Fig}
```
![image](https://user-images.githubusercontent.com/38340783/114512246-7b5c1c80-9c6b-11eb-9bdc-9262a319dd04.png)

**（3）表**
