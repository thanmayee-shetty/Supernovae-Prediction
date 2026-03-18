# Supernovae-Prediction

\documentclass[11pt]{article}
\usepackage[a4paper, margin=1in]{geometry}
\usepackage{hyperref}
\usepackage{graphicx}
\usepackage{enumitem}

\title{\textbf{Multimodal Supernova Progenitor Prediction}}
\author{}
\date{}

\begin{document}

\maketitle

\section*{Overview}
This project presents a \textbf{multimodal machine learning framework} to predict whether a \textbf{Red Supergiant (RSG)} star is likely to explode as a \textbf{Type II supernova}.

Unlike traditional approaches that focus on post-explosion data, this work predicts \textbf{pre-explosion likelihood} using:
\begin{itemize}
    \item Pre-explosion astronomical images
    \item Stellar catalog data
\end{itemize}

The model outputs a \textbf{probability score} indicating the likelihood of core collapse.

\section*{Key Idea}
The model combines:
\begin{itemize}
    \item Deep learning (CNN embeddings from images)
    \item Astrophysical tabular features
\end{itemize}

This fusion enables capturing both:
\begin{itemize}
    \item Visual morphology of stars
    \item Physical stellar properties (temperature, luminosity, etc.)
\end{itemize}

\section*{Architecture / Pipeline}
The system follows a multimodal pipeline:

\begin{enumerate}
    \item \textbf{Image Processing}
    \begin{itemize}
        \item Pre-explosion images from Pan-STARRS1
        \item Processed using ResNet-18
        \item Output: 512-dimensional embeddings
    \end{itemize}
    
    \item \textbf{Tabular Data Processing}
    \begin{itemize}
        \item Stellar parameters (Gaia DR3, 2MASS)
        \item Missing value imputation and scaling
    \end{itemize}
    
    \item \textbf{Feature Fusion}
    \begin{itemize}
        \item Concatenation of image and tabular features
    \end{itemize}
    
    \item \textbf{Model Training}
    \begin{itemize}
        \item Random Forest classifier with PCA
        \item Outputs explosion probability score
    \end{itemize}
\end{enumerate}

\section*{Dataset}
The dataset includes:
\begin{itemize}
    \item Confirmed supernova progenitors (positive samples)
    \item High-risk RSGs
    \item Normal RSGs (negative samples)
\end{itemize}

\textbf{Total size:} $\sim$986 samples with multimodal features.

\section*{Results}
The multimodal approach outperforms single-modality models:

\begin{itemize}
    \item Accuracy: $\sim$0.90
    \item F1 Score: $\sim$0.88
    \item AUC: $\sim$0.91
\end{itemize}

This demonstrates improved classification and probability calibration.

\section*{Key Contributions}
\begin{itemize}
    \item Pre-explosion supernova prediction framework
    \item Multimodal fusion of image and tabular data
    \item Interpretable probability-based predictions
    \item Application to astronomical candidate prioritization
\end{itemize}

\section*{Tech Stack}
\begin{itemize}
    \item Python
    \item PyTorch (Deep Learning)
    \item Scikit-learn (Random Forest, PCA)
    \item Astropy (FITS image processing)
\end{itemize}

\section*{Applications}
\begin{itemize}
    \item Early detection of supernova candidates
    \item Astronomical observation prioritization
    \item Astrophysical research
\end{itemize}

\section*{Future Work}
\begin{itemize}
    \item Incorporate time-series data
    \item Use advanced deep learning architectures
    \item Expand dataset with additional surveys
    \item Develop early-warning systems
\end{itemize}

\section*{Usage}
\begin{enumerate}
    \item Clone the repository
    \item Install dependencies
    \item Run preprocessing pipeline
    \item Train or load model
    \item Generate predictions
\end{enumerate}

\section*{Acknowledgements}
\begin{itemize}
    \item Gaia DR3
    \item Pan-STARRS1 Survey
    \item 2MASS
\end{itemize}

\end{document}
