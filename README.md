# HPE-Papers-List
공부할 논문 리스트


## Full-3D Supervision
Fully supervised 3D human pose estimation methods는 크게 2가지로 나뉜다.  

**i) end-to-end training**
 image나 video를 input으로 받고 directly로 3D poses를 estimates한다.  
 - [Lifting from the deep: Convolutional 3d pose estimation from a single image](https://openaccess.thecvf.com/content_cvpr_2017/papers/Tome_Lifting_From_the_CVPR_2017_paper.pdf) -CVPR 2017   
 - [3d human pose estimation using convolutional neural networks with 2d pose information](https://link.springer.com/content/pdf/10.1007/978-3-319-49409-8_15.pdf) - ECCV 2016   
 - [Deep kinematics analysis for monocular 3d human pose estimation](https://openaccess.thecvf.com/content_CVPR_2020/papers/Xu_Deep_Kinematics_Analysis_for_Monocular_3D_Human_Pose_Estimation_CVPR_2020_paper.pdf) - CVPR 2020  
 - [Integral human pose regression](https://openaccess.thecvf.com/content_ECCV_2018/papers/Xiao_Sun_Integral_Human_Pose_ECCV_2018_paper.pdf) - ECCV 2018  
 - [Cascaded deep monocular 3d human pose estimation with evolutionary training data](https://openaccess.thecvf.com/content_CVPR_2020/papers/Li_Cascaded_Deep_Monocular_3D_Human_Pose_Estimation_With_Evolutionary_Training_CVPR_2020_paper.pdf) - CVPR 2020  

**ii) two-step methods**  
 먼저 2D skeleton을 estimate하고 이 2D를 3D space로 lift한다.   
  - [3d human pose estimation = 2d pose estimation + matching.](https://openaccess.thecvf.com/content_cvpr_2017/papers/Chen_3D_Human_Pose_CVPR_2017_paper.pdf) - CVPR 2017  
  - [XNect: Real-time Multi-Person 3D Motion Capture with a Single RGB Camera](https://dl.acm.org/doi/pdf/10.1145/3386569.3392410) - ACM Transactions on Graphics (TOG) 2020  
  - [Ordinal depth supervision for 3d human pose estimation](https://openaccess.thecvf.com/content_cvpr_2018/papers/Pavlakos_Ordinal_Depth_Supervision_CVPR_2018_paper.pdf) - CVPR 2018   
  - [3d human pose estimation in video with temporal convolutions and semi-supervised training](https://openaccess.thecvf.com/content_CVPR_2019/papers/Pavllo_3D_Human_Pose_Estimation_in_Video_With_Temporal_Convolutions_and_CVPR_2019_paper.pdf) - CVPR 2019  
  - [Learning to fuse 2d and 3d image cues for monocular body pose estimation](https://openaccess.thecvf.com/content_ICCV_2017/papers/Tekin_Learning_to_Fuse_ICCV_2017_paper.pdf) - ICCV 2017  

두번째 approach가 large in-the wild 2D annotations에서 intermediate supervision의 장점이 있다.

현재 [A simple yet effective baseline for 3d human pose estimation](https://openaccess.thecvf.com/content_ICCV_2017/papers/Martinez_A_Simple_yet_ICCV_2017_paper.pdf) 와 [3d human pose estimation in video with temporal convolutions and semi-supervised training](https://openaccess.thecvf.com/content_CVPR_2019/papers/Pavllo_3D_Human_Pose_Estimation_in_Video_With_Temporal_Convolutions_and_CVPR_2019_paper.pdf)와 같은 lifting methods를 사용한 결과가 유망하다고 본다

## Temporal Supervision
 Temporal information은 occlusion이나 jittery 문제를 해결할수 있게 이전과 미래 human motion 정보를 제공한다.  
 
 - [3] : [Exploiting temporal context for 3d human pose estimation in the wild](https://openaccess.thecvf.com/content_CVPR_2019/papers/Arnab_Exploiting_Temporal_Context_for_3D_Human_Pose_Estimation_in_the_CVPR_2019_paper.pdf) - IEEV 2019    
 - [7] : [3d human pose estimation in video with temporal convolutions and semi-supervised training](https://openaccess.thecvf.com/content_CVPR_2019/papers/Pavllo_3D_Human_Pose_Estimation_in_Video_With_Temporal_Convolutions_and_CVPR_2019_paper.pdf) - CVPR 2019  
 - [11] : [Occlusion-aware networks for 3d human pose estimation in video](https://openaccess.thecvf.com/content_ICCV_2019/papers/Cheng_Occlusion-Aware_Networks_for_3D_Human_Pose_Estimation_in_Video_ICCV_2019_paper.pdf) - ICCV 2019  
 - [16] : [Exploiting temporal information for 3d human pose estimation](https://openaccess.thecvf.com/content_ECCV_2018/papers/Mir_Rayat_Imtiaz_Hossain_Exploiting_temporal_information_ECCV_2018_paper.pdf) - ECCV 2018  
 - [17] : [Vibe: Video inference for human body pose and shape estimation](https://openaccess.thecvf.com/content_CVPR_2020/papers/Kocabas_VIBE_Video_Inference_for_Human_Body_Pose_and_Shape_Estimation_CVPR_2020_paper.pdf) - CVPR 2020  
 - [30] : [Learning 3d human dynamics from video.](https://openaccess.thecvf.com/content_CVPR_2019/papers/Kanazawa_Learning_3D_Human_Dynamics_From_Video_CVPR_2019_paper.pdf) - CVPR 2019  
 - 
A long short-term memory (LSTM) sequence to sequence method는 video에서 temporal information을 사용하기를 제안하고 2D pose의 sequence에서부터 3D pose sequence를 predict한다.  
Sequence to sequence pose models는 drift하기 쉬운것을 보여준다.  

 [7]은 re-projection loss를 이용하여 semi-supervised training을 위해 temporal convolution network를 이용한다. 그러나 그것들의 re-projection scheme는 root trajectory를 estimate하는것을 요구한다. video에서 root trajectory를 estimating하는것은 어려운 task이다. 그러므로 그들은 small set of 3D annotations를 training 초기에 요구한다.  
[30]은 long sequences에서 drift에 robust하는 long history information을 이용하기 위해 확장된(dilated) convolutional network를 제안한다.
[17]은 또한 GRU encoder를 convolutional layers에 의해 생성된 pose information의 sequence를 encode하기 위해 사용한다.  



## Unpaired/Limited 3D supervision
limitied or unpaired 3D annotations을 얻는것이 full 3D annotations보다 훨씬 편하다.  
generative adversarial networks를 이용하는것은 unpaired 2D and 3D data를 이용하기 위해 광범위하게 연구되고있다.  

 - [6] : [Weakly-supervised discovery of geometry-aware representation for 3d human pose estimation](https://openaccess.thecvf.com/content_CVPR_2019/papers/Chen_Weakly-Supervised_Discovery_of_Geometry-Aware_Representation_for_3D_Human_Pose_Estimation_CVPR_2019_paper.pdf) - CVPR 2019  
 - [15] : [End-to-end recovery of human shape and pose](https://openaccess.thecvf.com/content_cvpr_2018/papers/Kanazawa_End-to-End_Recovery_of_CVPR_2018_paper.pdf) - CVPR 2018  
 - [20] : [Self-supervised 3d human pose estimation via part guided novel image synthesis](https://openaccess.thecvf.com/content_CVPR_2020/papers/Kundu_Self-Supervised_3D_Human_Pose_Estimation_via_Part_Guided_Novel_Image_CVPR_2020_paper.pdf) - CVPR 2020  
 - [38] : [Repnet: Weakly supervised training of an adversarial reprojection network for 3d human pose estimation](https://openaccess.thecvf.com/content_CVPR_2019/papers/Wandt_RepNet_Weakly_Supervised_Training_of_an_Adversarial_Reprojection_Network_for_CVPR_2019_paper.pdf) - CVPR 2019  
 - [43] : [3d human pose estimation in the wild by adversarial learning](https://openaccess.thecvf.com/content_cvpr_2018/papers/Yang_3D_Human_Pose_CVPR_2018_paper.pdf) - CVPR 2018  
 이 works에서 generator는 discriminator가 진짜와 가짜 3D poses를 구별할수 없게 real poses만큼 그럴듯한 3D fake poses를 estimate한다.  
 re-projection error를 보통 supervise training에 adversarial losses를 사용한다. [15],[38]

## Supervision without 3D  
input으로 오로지 multi-view data만을 필요로하는 3개의 유사한 works가 있다.  

 - [13] : [Weakly-supervised 3d human pose learning via multi-view images in the wild](https://openaccess.thecvf.com/content_CVPR_2020/papers/Iqbal_Weakly-Supervised_3D_Human_Pose_Learning_via_Multi-View_Images_in_the_CVPR_2020_paper.pdf) - CVPR 2020  
 - [18] : [Self-supervised learning of 3d human pose using multi-view geometry](https://openaccess.thecvf.com/content_CVPR_2019/papers/Kocabas_Self-Supervised_Learning_of_3D_Human_Pose_Using_Multi-View_Geometry_CVPR_2019_paper.pdf) - CVPR 2019  
  - [39] : [Canonpose: Self-supervised monocular 3d human pose estimation in the wild](https://openaccess.thecvf.com/content/CVPR2021/papers/Wandt_CanonPose_Self-Supervised_Monocular_3D_Human_Pose_Estimation_in_the_Wild_CVPR_2021_paper.pdf) - CVPR 2021 

[18]은 multi-view data로부터 triangualtion을 통해 pseudo 3D ground truth를 생성한다.  
이 간단한 approach는 2D keypoints가 아주 정확하면 효과적임을 보여준다.  
이 approach의 주요 한계는 input 2D keypoints에서 lack of robustness to error 이다.  

[13]은 x와 y coordinates로 부터 depth를 해결하는 2.5 training method를 제안하였다.  
그들은 x와 y를 estimating하기 위해 독립적인 2D annotation을 사용한다.  
depth를 estimation하기 위해, 모든 views로부터 estimated된 3D pose는 같아야만 함을 가정하며 서로 다른 views들로 부터 estimated된 3D poses들간의 multi-view consistency loss를 사용한다.  
비록 multi-view consistency사 강력함을 보여주지만, 두개의 잘못된 3D poses가 일관되었을때, indirect supervision에 모호함이 남아있다.  

[39]는 estimated된 3D poses의 multi-view re-projection을 2D로 되돌리는것을 제안한다.  
간단히 multi-view estimated 3D poses사이의 loss를 사용하는것 대신에, [39]는 re-projected 2D poses 간의 loss를 정의한다.  
3D에서 multi-view consistency를 비교하면, multi-view re-projection to 2D는 view-consistency enforcing에 더욱 유망함을 보여준다.  

모두 multi-view consistency를 이용한 방법이다

3D annotations의 부재에서, 정확한 2D poses는 정확한 multi-view re-projection에 아주 중요하다. Occluded body parts는 degenerated solutions로 이끈다. 그러므로 temporal lifting network를 사용하여 2D keypoints의 sequence로 부터 정보를 encode한다.  

EpipolarPose[18]과 유사하게, 본 논문은 lifting network를 train하기위해 pseudo ground truth 3D annotations를 생성한다. 그러나 적절한 views들에서부터 확실히 triangulation하기위해, 2D joint의 confidence를 통합한다. 게다가, training이 pseudo ground truth annotations에 완전히 의존하지 않기위해 multi-view re-projection loss를 사용한다. 


 - [Can 3d pose be learned from 2d projections alone?](https://openaccess.thecvf.com/content_ECCVW_2018/papers/11132/Drover_Can_3D_Pose_be_Learned_from_2D_Projections_Alone_ECCVW_2018_paper.pdf) - ECCV 2018  
 - [Weakly-supervised discovery of geometry-aware representation for 3d human pose estimation](https://openaccess.thecvf.com/content_CVPR_2019/papers/Chen_Weakly-Supervised_Discovery_of_Geometry-Aware_Representation_for_3D_Human_Pose_Estimation_CVPR_2019_paper.pdf) - CVPR 2019  

 - [Repnet: Weakly supervised training of an adversarial reprojection network for 3d human pose estimation](https://openaccess.thecvf.com/content_CVPR_2019/papers/Wandt_RepNet_Weakly_Supervised_Training_of_an_Adversarial_Reprojection_Network_for_CVPR_2019_paper.pdf) - CVPR 2019   
 - [Temporal hockey action recognition via pose and optical flows](https://openaccess.thecvf.com/content_CVPRW_2019/papers/CVSports/Cai_Temporal_Hockey_Action_Recognition_via_Pose_and_Optical_Flows_CVPRW_2019_paper.pdf) - CVPR Workshops 2019  
