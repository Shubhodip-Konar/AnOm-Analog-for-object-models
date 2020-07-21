# AnOm: Analog for Object models

Static reservoir modelling is a standard practice and integral to field development in in nearly every E&P company these days. Several algorithms are available for facies distribution in the modelling space, of which sequential indicator simulation (pixel based), object based and multiple point statistics (MPS) are being used most commonly. 
During appraisal phase and post appraisal field development planning, non availability of data forces geo-modellers to move to object based model, as it is mostly guided by interpretation of the facies bodies in a general conceptual depospace. The results thus become more geological and can explain connectivity and fluid flow in a more pragmatic way.  But in situations where minimal amount of core data is present and seismic cannot shed light about the channel parameters  (Figure 1), most of us resort to using analogs. 
This code snippet will assist geologists to quickly assess the probable channel parameters by analysing database collected from a large number of papers (Figure 2). The dataset will be kept live to facilitate addition

![image](https://user-images.githubusercontent.com/41413092/88035373-aba0df80-cb5f-11ea-99eb-5df5abea4230.png)

Fig. 1: Channel parameters explained in the schematics. Some of the parameters are explained in the image of Green river meanders taken from Earth observatory NASA .

![image](https://user-images.githubusercontent.com/41413092/88035581-033f4b00-cb60-11ea-97db-88bb365d9e36.png)

Fig. 2: Scatterplots of depth and width data present in the database

Bridge et al., 2000 identified the challenges associated with identification of maximum bankfull channel depth and proposed a method for calculating the same based on relationship of cross stratification, dune height and water depth.  But, in many cases non-representative or unavailable data forces geologists to use sand thickness from core or log data. Like any other geological analysis, this too has uncertainties associated with it. The first one is the sand thickness observed in the logs/ core with the actual depth of the river, mainly due to vertical accretion or lateral migration of channels and also due to drilling location (Figure 3). In short, the channel depths are not as deep as the preserved sandstone would suggest, and a variation of 1:1 to 0.3:1, with a mean at 0.55:1 can be seen in the published data (Fielding & Crane, 1987) (Figure 4). This observation is used to create the limiting distribution in this case.

![image](https://user-images.githubusercontent.com/41413092/88035733-384b9d80-cb60-11ea-8c83-b6ed4d4746a8.png)

Fig. 3: Uncertainties associated with sandstone thickness and channel depth

![image](https://user-images.githubusercontent.com/41413092/88036052-a4c69c80-cb60-11ea-8edb-a30225ced99e.png)
 
Fig. 4: Limiting cases for channel depth determination as per the bounding lines

The channel sand thickness is further decompacted (Figure 5) before prediction of the channel parameters as per the method described in Basin Analysis textbook by Allen and Allen (2013). 

![image](https://user-images.githubusercontent.com/41413092/88039701-89aa5b80-cb65-11ea-8451-fbd1b4508669.png)

Fig. 5: Decompaction method as described in Allen & Allen and the parameters used for the process

Post decompaction,  Statmodel OLS (ordinary least square regression) method is applied on the input database and the results are used to predict the channel parameters. The flow chart is added for the users to know about the workflow taken in the process (Figure 6). The geomodeller gets a distribution of results along with the results plotted on the input data. Along with this, channel parameters as described in Colombera, 2018 are also presented for comparison. The Github repository also has comments against the code for better understanding and modification at user discretion. 
Last but not the least, this code cannot replace the robust dataset already available through commercial enterprises. But with more number of dataset, a in place QC methods can make this usable to a bigger population without the access of commercial datasets or be used in dataroom situations for prompt uncomplicated but reasonably robust estimates.

![image](https://user-images.githubusercontent.com/41413092/88039841-b6f70980-cb65-11ea-9374-b1cefba729e9.png)

Fig. 6: Flow chart for AnOm: Analog for Object models

# Reference:

Colombera, L, Mountney, N.P, McCaffrey, W.D, 2013. A quantitative approach to fluvial facies models: methods and example results. Sedimentology, 60 (6). 1526 - 1558. ISSN 0037-0746

Colombera, L, Mountney, N.P, Medici, G, West, L.J., 2018. The geometry of fluvial channel bodies: Empirical characterization and implications for object-based models of the subsurface. AAPG Bulletin doi: 10.1306/10031817417 

Fielding, C.R. and Crane, R.C., 1987. An Application of Statistical Modelling to the prediction of Hydrocarbon Recovery Factors in Fluvial Reservoir Sequences. S.E.P.M. p321-327

Hove, A., Cobain, S., Bowyer, M., Colombera, L, Mountney, N.P, 2017. Quantifying uncertainties around Net Rock Volume: application of analogue-informed facies models. AAPG International Conference and Exhibition, London, England, October 15-18, 2017

Kästner, K., A. J. F. Hoitink, B. Vermeulen, T. J. Geertsema, and N. S. Ningsih, 2017. Distributary channels in the ﬂuvial to tidal transition zone, J. Geophys. Res. Earth Surf., 122, 696–710, doi:10.1002/2016JF004075

Leeder, M.R., 1973. Fluviatile fining-upwards cycles and the magnitude of palaeo-channels. Geological Magazine, v. 110,  p.265-276

Leopold, L.B. and Wolman, M.G., 1960. River Meanders: GSA Bulletin, v. 71, p. 769-794

Leuven, J.R.F.W., Maanen, B., Lexmond, B.R., Hoek, B.V., Spruijt, M.J., Kleinhans, M.G, 2018. Dimensions of fluvial-tidal meanders: are they disproportionally large?. Geology v. 46 (10), p.923-926

Marani, M., Lanzoni, S., Zandolin, D., Seminara, G., Rinaldo, A., 2002. Tidal meanders. Water Resources Research 38 (11)

Martin, J., Fernandes, A.M., Pickering, J., Howes, N., Mann,S., McNeil, K., 2018. The Stratigraphically Preserved Signature of Persistent Backwater Dynamics in a Large Paleodelta System: The Mungaroo Formation, North West Shelf, Australia.Journal of Sedimentary Research 88(7):850-872

Sidorchuk, A., Borisova, O., Chernov, A., Panin, A, 2013. Three Main stages of floodplain evolution in northern Eurasia and their ecological significance. Floodplains: Environmental management, restoration and ecological implications, Nova Publishers

Sutter. A, 2008. Sedimentology, Depositional Environments and Sequence Stratigraphy, accessed on 10th May, 2020

Sylvester, Z, 2017. Exploring (de)compaction with Python, accessed on 13th May, 2020

Zhang, X, 2014, Lacustrine turbidites from tropical African lakes as indicators of hydrologic and climatic changes: Ph. D. thesis, Syracuse University


