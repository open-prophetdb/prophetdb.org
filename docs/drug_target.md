---
title: "OpenProphetDB"
hide:
  - navigation
  - toc
  - footer
---

<div class="timeline-container">
    <div class="timeline-header">
        <h1><i class="fas fa-project-diagram"></i>&nbsp;From Literature to Drug Repurposing & Target Identification</h1>
        <p>A complete knowledge graph pipeline from literature annotation to drug repurposing & target identification</p>
    </div>
    
    <div class="timeline">
        <!-- Step 1: Literature Annotation -->
        <div class="timeline-item">
            <div class="timeline-marker step-1">
                <i class="fas fa-highlighter"></i>
            </div>
            <div class="card timeline-card">
                <div class="step-number step-1">1</div>
                <div class="card-header">
                    <h5 class="card-title">Network Medicine Extension</h5>
                    <p class="card-subtitle">Literature Annotation</p>
                </div>
                <div class="image-placeholder">
                    <img src="/assets/images/network-medicine-extension.png" alt="Network Medicine Extension">
                </div>
                <div class="card-body">
                    <p class="card-text">
                        This extension enables biomedical researchers to curate, annotate, and synchronize literature-derived findings. It is used to extract and standardize biomedical knowledge from literature.
                    </p>
                    <div class="btn-group d-flex">
                        <a href="https://github.com/open-prophetdb/network-medicine-extension" class="btn btn-primary" target="_blank">
                            <i class="fab fa-github"></i> GitHub
                        </a>
                        <a href="https://chromewebstore.google.com/detail/network-medicine-extensio/eamandgbalpjppofkhbefbbhckkkengp?authuser=0&hl=en" class="btn btn-outline-secondary" target="_blank">
                            <i class="fab fa-chrome"></i> Install Chrome Extension
                        </a>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- Step 2: Knowledge Graph Construction -->
        <div class="timeline-item">
            <div class="timeline-marker step-2">
                <i class="fas fa-sitemap"></i>
            </div>
            <div class="card timeline-card">
                <div class="step-number step-2">2</div>
                <div class="card-header">
                    <h5 class="card-title">BioMedGPS Data</h5>
                    <p class="card-subtitle">Knowledge Graph Builder</p>
                </div>
                <div class="image-placeholder">
                    <img src="/assets/images/kg-builder.png" alt="BioMedGPS Data">
                </div>
                <div class="card-body">
                    <p class="card-text">
                        A biomedical knowledge graph builder responsible for integrating data from literature annotation to build a large-scale structured knowledge graph. This is the key step connecting the original literature data to downstream analysis.
                    </p>
                    <div class="btn-group d-flex">
                        <a href="https://github.com/open-prophetdb/biomedgps-data" class="btn btn-primary" target="_blank">
                            <i class="fab fa-github"></i> GitHub
                        </a>
                        <a href="https://open-prophetdb.github.io/biomedgps-data/" class="btn btn-outline-secondary" target="_blank">
                            <i class="fas fa-book"></i> Documentation
                        </a>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- Step 3: Graph Neural Network -->
        <div class="timeline-item">
            <div class="timeline-marker step-3">
                <i class="fas fa-brain"></i>
            </div>
            <div class="card timeline-card">
                <div class="step-number step-3">3</div>
                <div class="card-header">
                    <h5 class="card-title">DGL-KE</h5>
                    <p class="card-subtitle">Graph Neural Network Model</p>
                </div>
                <div class="image-placeholder">
                    <img src="/assets/images/model-performance.png" alt="BioMedGPS Explainer">
                </div>
                <div class="card-body">
                    <p class="card-text">
                        A high-performance, easy-to-use, and scalable large-scale knowledge graph embedding learning package. Using graph neural network technology to perform deep learning on the knowledge graph, providing a foundation for subsequent prediction analysis.
                    </p>
                    <div class="btn-group d-flex">
                        <a href="https://github.com/open-prophetdb/dgl-ke" class="btn btn-primary" target="_blank">
                            <i class="fab fa-github"></i> GitHub
                        </a>
                        <a href="https://wandb.ai/yjcyxky/biomedgps-kge-v1?nw=nwuseryjcyxky" class="btn btn-outline-secondary" target="_blank">
                            <i class="fas fa-chart-line"></i> Weights & Biases
                        </a>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- Step 4: Prediction and Interpretation -->
        <div class="timeline-item">
            <div class="timeline-marker step-4">
                <i class="fas fa-search"></i>
            </div>
            <div class="card timeline-card">
                <div class="step-number step-4">4</div>
                <div class="card-header">
                    <h5 class="card-title">BioMedGPS Explainer</h5>
                    <p class="card-subtitle">Prediction & Interpretation</p>
                </div>
                <div class="image-placeholder">
                    <img src="/assets/images/prediction.jpeg" alt="BioMedGPS Explainer">
                </div>
                <div class="card-body">
                    <p class="card-text">
                        A comprehensive drug repurposing and visualization toolkit based on network medicine, designed for biomedical research. Using the trained model to predict drug repurposing and provide detailed explanations and visualizations.
                    </p>
                    <div class="btn-group d-flex">
                        <a href="https://github.com/open-prophetdb/biomedgps-explainer" class="btn btn-primary" target="_blank">
                            <i class="fab fa-github"></i> GitHub
                        </a>
                        <a href="https://open-prophetdb.github.io/biomedgps-explainer/" class="btn btn-outline-secondary" target="_blank">
                            <i class="fas fa-book"></i> Documentation
                        </a>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- Step 5: Online Platform -->
        <div class="timeline-item">
            <div class="timeline-marker step-5">
                <i class="fas fa-globe"></i>
            </div>
            <div class="card timeline-card">
                <div class="step-number step-5">5</div>
                <div class="card-header">
                    <h5 class="card-title">Network Medicine Platform</h5>
                    <p class="card-subtitle">Online Platform</p>
                </div>
                <div class="image-placeholder">
                    <img src="/assets/images/network-medicine-webpage.png" alt="Network Medicine Platform">
                </div>
                <div class="card-body">
                    <p class="card-text">
                        An online platform for drug repurposing and disease mechanism research based on knowledge graphs and graph neural networks. Integrates the results of all previous steps, providing a complete network medicine analysis service to users.
                    </p>
                    <div class="btn-group d-flex">
                        <a href="https://github.com/open-prophetdb/biomedgps" class="btn btn-primary" target="_blank">
                            <i class="fab fa-github"></i> GitHub
                        </a>
                        <a href="https://drugs.3steps.cn" class="btn btn-outline-secondary" target="_blank">
                            <i class="fas fa-external-link-alt"></i> Online Access
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </div>
</div>
