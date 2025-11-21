\documentclass[10pt, letterpaper]{article}

% Packages:
\usepackage[
    ignoreheadfoot, % set margins without considering header and footer
    top=1.2 cm, % Reduced top margin
    bottom=1.2 cm, % Reduced bottom margin
    left=1.2 cm, % Reduced left margin
    right=1.2 cm, % Reduced right margin
    footskip=0.5 cm, % Reduced separation between body and footer
    % showframe % for debugging
]{geometry} % for adjusting page geometry
\usepackage{titlesec} % for customizing section titles
\usepackage{tabularx} % for making tables with fixed width columns
\usepackage{array} % tabularx requires this
\usepackage[dvipsnames]{xcolor} % for coloring text
\definecolor{primaryColor}{RGB}{0, 79, 144} % define primary color
\usepackage{enumitem} % for customizing lists
\usepackage{fontawesome5} % for using icons
\usepackage{amsmath} % for math
\usepackage[
    pdftitle={Vidit Rastogi's CV},
    pdfauthor={Vidit Rastogi},
    pdfcreator={LaTeX with RenderCV},
    colorlinks=true,
    urlcolor=primaryColor
]{hyperref} % for links, metadata and bookmarks
\usepackage[pscoord]{eso-pic} % for floating text on the page
\usepackage{calc} % for calculating lengths
\usepackage{bookmark} % for bookmarks
\usepackage{lastpage} % for getting the total number of pages
\usepackage{changepage} % for one column entries (adjustwidth environment)
\usepackage{paracol} % for two and three column entries
\usepackage{ifthen} % for conditional statements
\usepackage{needspace} % for avoiding page brake right after the section title
\usepackage{iftex} % check if engine is pdflatex, xetex or luatex

% Ensure that generate pdf is machine readable/ATS parsable:
\ifPDFTeX
    \input{glyphtounicode}
    \pdfgentounicode=1
    % \usepackage[T1]{fontenc} % this breaks sb2nov
    \usepackage[utf8]{inputenc}
    \usepackage{lmodern}
\fi

% Some settings:
\AtBeginEnvironment{adjustwidth}{\partopsep0pt} % remove space before adjustwidth environment
\pagestyle{empty} % no header or footer - already present and good!
\setcounter{secnumdepth}{0} % no section numbering
\setlength{\parindent}{0pt} % no indentation
\setlength{\topskip}{0pt} % no top skip
\setlength{\columnsep}{0cm} % set column seperation

% Removed custom footer style as it's not needed with pagestyle{empty}
% \makeatletter
% \let\ps@customFooterStyle\ps@plain % Copy the plain style to customFooterStyle
% \patchcmd{\ps@customFooterStyle}{\thepage}{
%    \color{gray}\textit{\small John Doe - Page \thepage{} of \pageref*{LastPage}}
% }{}{} % replace number by desired string
% \makeatother
% \pagestyle{empty} % Already set above, redundant here.

% Adjusted title formatting for less vertical space
\titleformat{\section}{\needspace{2\baselineskip}\bfseries\large}{}{0pt}{}[\vspace{0.05pt}\titlerule] % Reduced space before rule

\titlespacing{\section}{-1pt}{0.02 cm}{0.05 cm}


\renewcommand\labelitemi{$\circ$} % custom bullet points
\newenvironment{highlights}{
    \begin{itemize}[
        topsep=0.05 cm, % Reduced space before the first item
        parsep=0.05 cm, % Reduced space between paragraphs within an item
        partopsep=0pt,
        itemsep=0pt, % Reduced space between items
        leftmargin=0.4 cm + 10pt
    ]
}{
    \end{itemize}
} % new environment for highlights

\newenvironment{highlightsforbulletentries}{
    \begin{itemize}[
        topsep=0.01 cm,
        parsep=0.05 cm, % Reduced parsep
        partopsep=0pt,
        itemsep=0pt,
        leftmargin=10pt
    ]
}{
    \end{itemize}
} % new environment for highlights for bullet entries


\newenvironment{onecolentry}{
    \begin{adjustwidth}{
        0.2 cm + 0.00001 cm
    }{
        0.2 cm + 0.00001 cm
    }
}{
    \end{adjustwidth}
} % new environment for one column entries

\newenvironment{twocolentry}[2][]{
    \onecolentry
    \def\secondColumn{#2}
    \setcolumnwidth{\fill, 4.5 cm}
    \begin{paracol}{2}
}{
    \switchcolumn \raggedleft \secondColumn
    \end{paracol}
    \endonecolentry
} % new environment for two column entries

\newenvironment{header}{
    \setlength{\topsep}{0pt}\par\kern\topsep\centering\linespread{1.2} % Reduced linespread in header
}{
    \par\kern\topsep
} % new environment for the header


% save the original href command in a new command:
\let\hrefWithoutArrow\href

% new command for external links:
\renewcommand{\href}[2]{\hrefWithoutArrow{#1}{\ifthenelse{\equal{#2}{}}{ }{#2 }\raisebox{.15ex}{\footnotesize \faExternalLink*}}}


\begin{document}
    \newcommand{\AND}{\unskip
        \cleaders\copy\ANDbox\hskip\wd\ANDbox
        \ignorespaces
    }
    \newsavebox\ANDbox
    \sbox\ANDbox{}

    \placelastupdatedtext
    \begin{header}
        \textbf{\fontsize{18.8 pt}{18 pt}\selectfont VIDIT RASTOGI}
    

        \normalsize
        \small
        Delhi \textbar\ 
        \hrefWithoutArrow{mailto:viditrastogi2005@gmail.com}{viditrastogi2005@gmail.com} \textbar\ 
        \hrefWithoutArrow{tel:+918130302618}{8130302618} \textbar\ 
        \hrefWithoutArrow{https://www.linkedin.com/in/vr2005}{linkedin.com/in/vr2005} \textbar\ 
        \hrefWithoutArrow{https://github.com/V2005R}{github.com/V2005R}
    \end{header}
    \section{Education}

        \begin{twocolentry}{
        \textbf{2022 - 2026}}
            \textbf{Vellore Institute Of Technology, Bhopal(Pursuing)}
        \end{twocolentry}


        \begin{twocolentry}{
        \textit{CGPA: 8.25/10}}
            \textit{B.Tech Computer Science and Engineering}
        \end{twocolentry}


        \begin{twocolentry}{
        \textbf{2021 - 2022}}
            \textbf{Maharaja Agarsain Public School, New Delhi, India}
        \end{twocolentry}


        \begin{twocolentry}{
        \textit{80.33\%}} % Added % here
            \textit{12th (CBSE)}
        \end{twocolentry}


        \begin{twocolentry}{
        \textbf{2019 - 2020}}
            \textbf{Maharaja Agarsain Public School, New Delhi, India}
        \end{twocolentry}


        \begin{twocolentry}{
        \textit{71.40\%}} % Added % here
            \textit{10th (CBSE)}
        \end{twocolentry}    
    
    \section{Experience}
        \begin{twocolentry}{   
        \textbf{June 2025 – July 2025}}
            \textbf{Thinking Hats Entertainment Solutions Limited, India}
        \end{twocolentry}
        
        \begin{twocolentry}{   
        \textit{}}
            \textit{Software Engineer Intern}
        \end{twocolentry}
        
        
        \begin{onecolentry}
            \begin{highlights}
        \item Engineered and streamlined backend database systems to support internal analytics tools and improve overall data handling efficiency.
        \item Collaborated with a cross-functional tech team to analyze system bottlenecks and optimize SQL queries, improving performance through structured diagnostics and iterative development.
        \item Achieved a 3\% improvement in data retrieval speed, directly enhancing tool responsiveness and contributing to improved internal workflow reliability.
    \end{highlights}
        \end{onecolentry}


        
    \section{Projects}

\begin{twocolentry}{\textbf{Mar 2025 – April 2025}}
        \textbf{\hrefWithoutArrow{https://github.com/V2005R/VentureVision}{\color{blue}{VentureVision}}}
\end{twocolentry}

\begin{twocolentry}{}
    \textit{Python, Pandas, Matplotlib, Random-Forest, Scikit-Learn}
\end{twocolentry}

\begin{onecolentry}
    \begin{highlights}
        \item Conducted comprehensive market research on 6,000+ startups across multiple sectors and funding stages.
        \item Applied data analytics and predictive modeling (Random Forest, Python, Pandas) to identify key drivers of startup success.
        \item Delivered strategic insights with 94\% prediction accuracy, enabling more informed investment and growth decisions.
    \end{highlights}
\end{onecolentry}

\begin{twocolentry}{\textbf{Feb 2025 – Mar 2025}}
        \textbf{\hrefWithoutArrow{https://github.com/V2005R/Flight-Mundus}{\color{blue}{Flight-Mundus}}}%
\end{twocolentry}

\begin{twocolentry}{}
    \textit{Python, Pandas, Matplotlib, XGBoost, Scikit-Learn}
\end{twocolentry}

\begin{onecolentry}
    \begin{highlights}
        \item Investigated operational inefficiencies by analyzing 484,000+ flight records covering routes, schedules, and weather.
        \item Designed a predictive model using XGBoost and performance metrics to highlight delay risk factors.
        \item Provided actionable insights with 92\% accuracy, supporting operational strategy, risk mitigation, and efficiency improvements.
    \end{highlights}
\end{onecolentry}

\begin{twocolentry}{\textbf{Jan 2025 – Feb 2025}}
        \textbf{\hrefWithoutArrow{https://github.com/V2005R/GlycoVision}{\color{blue}{GlycoVision}}}%
\end{twocolentry}

\begin{twocolentry}{}
    \textit{Python, Pandas, OpenCV, Inception V3-ResNet}
\end{twocolentry}

\begin{onecolentry}
    \begin{highlights}
        \item Researched diabetic retinopathy patterns to address a critical healthcare challenge.
        \item Integrated advanced AI (Inception-ResNetV2, OpenCV) with structured data analysis to classify medical risk severity levels.
        \item Developed a scalable decision-support tool with 79\% accuracy, demonstrating potential for strategic healthcare planning and patient risk assessment.
    \end{highlights}
\end{onecolentry}



    
    \section{Technical Skills}
        \begin{onecolentry}
            \textbf{Skills:} Data Structures and Algorithms, OOPS, Machine Learning, Cross-team Collaboration, Data-driven Decision Making, Market Research
        \end{onecolentry}

        
        \begin{onecolentry}
            \textbf{Languages:} Python, SQL
        \end{onecolentry}


        \begin{onecolentry}
            \textbf{Technologies/Frameworks:} Git/GitHub, Pandas, Numpy, Scikit-learn, XGBoost, TensorFlow, PyTorch, Keras, OpenCV, Matplotlib, MySQL, Streamlit, AWS, Hubspot, VBA, Tableau, Power BI, API Integration
        \end{onecolentry}


    \section{Extracurricular}
        \begin{twocolentry}{   
        \textbf{Sep 2023 - Oct 2023}}
            \textbf{Software Development Club, VIT}
        \end{twocolentry}
    

        \begin{twocolentry}{   
        \textit{VIT, Bhopal}}
            \textit{Side Core Committee Member}
        \end{twocolentry}
        \begin{onecolentry}
            \begin{highlights}
                \item Designed and executed engagement strategies to increase member participation, driving higher involvement in events and workshops.
                \item Supported strategic planning and execution of club activities by aligning editorial, technical, and event-management efforts with the club’s growth objectives.
            \end{highlights}
        \end{onecolentry}
        

        
    \section{Certificates}
        \begin{onecolentry}
    \begin{highlights}
        \item \textbf{\hrefWithoutArrow{https://drive.google.com/file/d/1raMwFfUliwlPFFmQDSXMbIvhE9aaTSv3/view?usp=drive_link}{Application Integration Professional (Oracle)}}
        \item \textbf{\hrefWithoutArrow{https://skillwallet.smartinternz.com/internships/google_developers/86174520c23c6c61f0f50da7294b9f13}{Artificial Intelligence (Google)}}
        \item \textbf{\hrefWithoutArrow{https://courses.ibmcep.cognitiveclass.ai/certificates/c8364951784c400a9226a02dfda4633b}{Blockchain Developer (IBM)}}
        \item \textbf{\hrefWithoutArrow{https://www.mygreatlearning.com/certificate/OVGYXUWJ}{Free Crash Course in Machine Learning}}
        \item \textbf{\hrefWithoutArrow{https://coursera.org/verify/HGRDRBD6VUAP}{The Bits and Bytes of Computer Networking (Google)}}
    \end{highlights}
        \end{onecolentry}        
\end{document}
