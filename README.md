java c
ELEC ENG 3110 Electric Power Systems
ELEC ENG 7074 Power Systems PG
(Semester 2, 2024)
Assignment 1:
Power System Frequency Control
(Due 23:00 Fri. 20September 2024 myUni Submission)
Investigation of power system frequency control using simplified models.The objective of this assignment is to investigate some aspects of power system frequency con- trol using simplified models. The investigation is intended to provide conceptual insights only. The models are not necessarily optimized to yield the best frequency control performance. The Mathworks Simulink program, which is a companion of Matlab, will be employed to build and simulate dynamic models of the systems. Thus, the assignment will also provide an opportunity for you to become familiar with a very widely used tool for simulating dynamic systems.The deliverable outcome is to be an engineering technical report that clearly and concisely de- tails the conduct and findings of your investigation and clear and pointed discussion of the tech- nical and engineering significance of your findings. The report  should address each of the matters and questions listed in the scope of work in Section 3. Credit will be given for innova- tive studies and analysis that either reveal other aspects of system performance or which im- prove the performance of the system.It is recommended that you follow the guidelines for writing technical engineering reports pro- duced by The Institute of Engineering Technology and which are available at the following web-site: https://www.theiet.org/media/5182/technical-report-writing.pdfWith reference to the above guidelines your report is expected to convey information to other engineers about key aspects of the performance of the system and it is intended for selective reading. The latter point means that you should organize your report into numbered sections with informative headings.
It is strongly recommend that you approach this assignment in the same way as you would as a professional engineer conducting the project for an employer or client.
Introductory analysis is presented in Section 1 to assist in the systematic formulation of the fre- quency control model.
1      Introductory AnalysisThe objective is to explore the performance of the system frequency control system as the mix of generation sources is varied. We are interested in assessing performance for different propor- tions of synchronous and asynchronous generation and how the performance of the overall fre- quency control system performs as different proportions of generation capacity are equipped with primary frequency control. The overall structure of the system model is shown in Figure 1. In this model the equivalent generator model represents the effective inertial response of the system taking into consideration that a proportion of the generation is asynchronous. A propor- tion of both the synchronous and asynchronous generation sources are not equipped with fre- quency controls and therefore do not contribute to the control of system frequency. A proportion of synchronous sources are equipped with governors which control the speed of their generators and a proportion of asynchronous sources are also equipped with frequency controllers that are used to regulate their power output so as to control system frequency.
Figure 1: Simplified model of system frequency control containing synchronous and
asynchronous sources. (Note that blocks with no input signal represent a fixed or constant
input to the model with the value shown in the block.)
1.1         Per-unit scaling and specification of generation capacitiesWe will use the total online generation capacity (Sb  in MW) as the base value of power. Thus, a power system load, Pl , of 0.8 per-unit means that the system is consuming 80% of the rated on-line generation capacity. (Note: We will see below that it is not necessary to specify the ac- tual value of Sb ).
To facilitate this exploration the total online generation capacity is divided into a number of components.Sb  =  Ssb + Sab                                                                                (1)
where Ssb  and Sab  are respectively the online synchronous and online non-synchronous (or asynchronous) generation capacity.Ssb  =  αsbSb  and Sab   =  ( 1 – αsb )Sb                                                         (2)
where αsb  is the specified proportion of the total online generation capacity which is synchro- nous.The online synchronous generation capacity is then partitioned into the following components:Ssb  =  Sspb + Ssub  where                                                     (3)Sspb  =  αspbSsb  =  αspb αsbSb  and Ssub   =  ( 1 – αspb )Ssb  =  ( 1 – αspb )αsbSb               (4)
are respectively the proportion of online synchronous generation capacity with primary govern- ing control and the balance of online synchronous generation capacity i代 写ELEC ENG 3110 Electric Power Systems ELEC ENG 7074 Power Systems PG Semester 2, 2024 Assignment 1Matlab
代做程序编程语言s ungoverned.The online asynchronous generation capacity is similarly partitioned into a fraction with prima- ry governing control, Sapb, and the balance of asynchronous generation which is ungoverned, Saub , where:
Sab  =  Sapb + Saub  and                                                           (5)
Sapb  =  αapbSab  =  αapb ( 1 – αsb )Sb  
Saub  =  ( 1 – αapb )Sab  =  ( 1 – αapb )( 1 – αsb )Sb                   (6)
Thus, to define the online capacities of the different types of generation represented in our mod- el the parameters αsb , αspb  and αapb  must be specified.For example, if αsb   =  0.8  then 80% of all online generation capacity is synchronous and the balance 1 – αsb  =  0.2  (i.e. 20%) is asynchronous. If αspb   =  0.4  then 40% of the online syn- chronous generation capacity is under primary frequency control and the balance of such gen- eration   (i.e.   60%)   is   not   under   frequency   control.   In   this   example   it   means   that αsb × αspb  =  0.8 × 0.4  =  0.32  or just 32% of all online capacity is under primary frequency control.
1.2         Specification of the initial generation outputIn this model we specify the initial power output from each of the generation sources. On the basis of this specification the initial system load is determined, on the assumption that the sys- tem is lossless.The initial power output from the online synchronous generation with primary speed control is specified as a fraction βsp  of the specified online capacity Sspb  of this type of generation. The initial power output is expressed in per-unit of Sb . 
The initial output from the other types of generation are similarly specified as follows:
Pmsu0    =  βsu ( 1 – αspb )αsb
Pmap0    =  βap αapb ( 1 – αsb )         pu on Sb .
Pmau0    =  βau ( 1 – αapb )( 1 – αsb )
The initial power output from the synchronous generation sources is:
P      = P       + P
ms0                 msp0             msu0
and the initial power output from the asynchronous generation sources is:
P       = P       + P
ma0                 map0             mau0
and finally, the initial output from all generation sources is,P     = P     + P      .                                                        (11)Thus, to define the initial steady-state operating point of the system it is necessary to specify
βsp, βsu, βap  and βau .
It is important to distinguish between online capacity of the various generation categories and the actual (initial) power output from each of these generation categories. Thus, if, for example,βsp  =  0.5  then it means that initially the power output of the online synchronous generation capacity  that  is  under primary  frequency  control  is  50%.  If,  furthermore,  αb   =  0.8   and αspb  =  0.4 it follows that the initial power output from all online synchronous generation ca- pacity that is under primary frequency control is:
Pmsp0    =  βsp ( αspb αb )  =  0.5 × (0.8 × 0.4)  =  0.16  pu of Sb .
1.3         Equivalent generator rotor dynamics
The transfer-function block diagram of the equivalent generator of the system is shown in Fig- ure 2.
Figure 2: Equivalent generator rotor dynamics for system
load / frequency analysis.
1.3.1       Specification of the inertia constantThe inertia constant of online synchronous generation limits the rate of change of frequency. In the model we specify the inertia constant, Hs, in per-unit of the on-line synchronous generation capacity. Typically, Hs   =  3.5 pu on Ssb .
For use in the model this inertia constant must be converted to per-unit on Sb . Thus,
1.3.2       Frequency dependent load
The system load is linearly dependent on the system-frequency perturbation as followsPl (f) =  (Pl0 + ΔPl0)( 1 + DΔf)                                      (13)where f  =  ( 1 + Δf) pu is the system frequency in per-unit of the system nominal synchronous frequency, f0  =  50 Hz, Δf  is the per-unit perturbation of the system frequency and Pl0    is the initial steady-state value of the load. Note that under initial steady-state conditions the system is operating at synchronous frequency, i.e. Δf0  =  0 pu. Pl0  is the initial steady-state load on the system assuming that the system is initially operating at 50 Hz; and ΔPl0  is the applied change in system load at the nominal system frequency of 50 Hz
1.3.3       Composite rotor equation of motion for the analysis of system-frequency controls The acceleration equation of the system is, as detailed in the lectures,= Pm – Pl  in pu of Sb                                                               (14)where Pm  and Pl  are respectively the generation and load, Δf  is the per-unit system-frequency perturbation and H is as defined in (12). The block diagram of this equation, including the fre- quency dependence of the load, is shown in Figure 2.





         
加QQ：99515681  WX：codinghelp
