**（1）图占双栏**
```
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
```
%样式写法
\renewcommand\arraystretch{1.3}
\begin{table}[!htbp]                  %若双栏此处改成\begin{table*}[hb]
\centering
\setlength{\abovecaptionskip}{0pt}%    
\caption{Simulation Parameters}
\label{tab:Simulation Parameters}
\ 
\newline
\begin{tabular*}{\linewidth}{lll}
\hline
\hline
{\bf Category} & {\bf Parameter} & {\bf Default Value} \\
\hline
Sumo & Scene Information & Munich City, \\ 
  &  & Arrival Rate (1,1.43,2) Veh/s \\
  &  & Single Signal Intersection, \\
  &  & Single Junction (20,40,60) Veh \\
  &  & Bologna City, \\
  &  & Real Traffic Flow in 8:00-9:00 \\
  & Detector Length & (40,50,60,...,140) m \\
  &  & Automatic Adjust, min 40m \\
\hline
Veins & Beacon Rate & 1HZ \\
  & Transmission Power & 20mW \\
\hline
Tracker & Eavesdropper Range & 300m \\
  & Eavesdropper Position & Full Coverage and Overlap 30m \\
  & Track Interval & 1s\\
\hline
\hline
\end{tabular*}
\end{table}                   %若双栏此处改成\end{table*}


%文章中引用
Table \ref{tab:Simulation Parameters}
```
![image](https://user-images.githubusercontent.com/38340783/114513165-7ba8e780-9c6c-11eb-960a-0449db60c2d4.png)

**（4）算法**
```
\begin{algorithm}[!htbp] %算法开始 
\caption{TLAS Simulation Algorithm} %算法的题目 
\label{alg4.1} %算法的标签 
\begin{algorithmic}[1] %此处的[1]控制一下算法中的每句前面都有标号 

\REQUIRE Map status $map$, The current time $t$.
\ENSURE Latest TLAS location information $POS_{SM}$, \\ \quad \quad \ Vehicle silence status status[$vehicle$].
\STATE $I_{SM},POS_{SM}$ = getRSUBeacon($t$)
\FORALL {$vehicles$ $\epsilon$ $map$}
    \IF {getPos($vehicle$) in $POS_{SM}$}
        \IF {$I_{SM}$ == 0}
            \STATE status[$vehicle$] = nosilent
            \STATE $N_{vehicle}$ = setRefreshClock()
            \IF {greenLight in end}
                \STATE totalVehicle = setPredictModel($N_{vehicle}$,greenLight.time())
                \STATE $POS_{SM}$ = setNewLength()
                \STATE setRefreshBeacon()
            \ENDIF
        \ELSE 
            \STATE status[$vehicle$] = silent
            \STATE setSilent(vehicle)
        \ENDIF
    \ENDIF
\ENDFOR 

\end{algorithmic} 
\end{algorithm}


%文章中引用
Algorithm \ref{alg4.1}
```
![image](https://user-images.githubusercontent.com/38340783/114513640-fd991080-9c6c-11eb-9ca5-cf91cd804973.png)




