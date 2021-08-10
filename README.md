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
 Temporal information은 occlusion이나 jittery 문제를 해결할수 있게 이전과 미래 human motions의 지식을 제공한다.  
 - [Exploiting temporal context for 3d human pose estimation in the wild](https://openaccess.thecvf.com/content_CVPR_2019/papers/Arnab_Exploiting_Temporal_Context_for_3D_Human_Pose_Estimation_in_the_CVPR_2019_paper.pdf) - IEEV 2019    
 - [3d human pose estimation in video with temporal convolutions and semi-supervised training](https://openaccess.thecvf.com/content_CVPR_2019/papers/Pavllo_3D_Human_Pose_Estimation_in_Video_With_Temporal_Convolutions_and_CVPR_2019_paper.pdf) - CVPR 2019  
 - [Occlusion-aware networks for 3d human pose estimation in video](https://openaccess.thecvf.com/content_ICCV_2019/papers/Cheng_Occlusion-Aware_Networks_for_3D_Human_Pose_Estimation_in_Video_ICCV_2019_paper.pdf) - ICCV 2019  
 - [Exploiting temporal information for 3d human pose estimation](https://openaccess.thecvf.com/content_ECCV_2018/papers/Mir_Rayat_Imtiaz_Hossain_Exploiting_temporal_information_ECCV_2018_paper.pdf) - ECCV 2018  
 - [Vibe: Video inference for human body pose and shape estimation](https://openaccess.thecvf.com/content_CVPR_2020/papers/Kocabas_VIBE_Video_Inference_for_Human_Body_Pose_and_Shape_Estimation_CVPR_2020_paper.pdf) - CVPR 2020  
 - [Learning 3d human dynamics from video.](https://openaccess.thecvf.com/content_CVPR_2019/papers/Kanazawa_Learning_3D_Human_Dynamics_From_Video_CVPR_2019_paper.pdf) - CVPR 2019  


## Unpaired/Limited 3D supervision
 제안되고 unpaired한 3D annotation을 얻는것이 full 3D annotations 보다 편리하다.    
 unpaired한 2D 와 3D data를 사용하기위해 generative adversarial network가 광범위하게 연구되어왔다.   
 - [Weakly-supervised discovery of geometry-aware representation for 3d human pose estimation](https://openaccess.thecvf.com/content_CVPR_2019/papers/Chen_Weakly-Supervised_Discovery_of_Geometry-Aware_Representation_for_3D_Human_Pose_Estimation_CVPR_2019_paper.pdf) - CVPR 2019  
 - [End-to-end recovery of human shape and pose](https://openaccess.thecvf.com/content_cvpr_2018/papers/Kanazawa_End-to-End_Recovery_of_CVPR_2018_paper.pdf) - CVPR 2018  
 - [Self-supervised 3d human pose estimation via part guided novel image synthesis](https://openaccess.thecvf.com/content_CVPR_2020/papers/Kundu_Self-Supervised_3D_Human_Pose_Estimation_via_Part_Guided_Novel_Image_CVPR_2020_paper.pdf) - CVPR 2020  
 - [Repnet: Weakly supervised training of an adversarial reprojection network for 3d human pose estimation](https://openaccess.thecvf.com/content_CVPR_2019/papers/Wandt_RepNet_Weakly_Supervised_Training_of_an_Adversarial_Reprojection_Network_for_CVPR_2019_paper.pdf) - CVPR 2019  
 - [3d human pose estimation in the wild by adversarial learning](https://openaccess.thecvf.com/content_cvpr_2018/papers/Yang_3D_Human_Pose_CVPR_2018_paper.pdf) - CVPR 2018  

## Supervision without 3D 
 - [Can 3d pose be learned from 2d projections alone?](https://openaccess.thecvf.com/content_ECCVW_2018/papers/11132/Drover_Can_3D_Pose_be_Learned_from_2D_Projections_Alone_ECCVW_2018_paper.pdf) - ECCV 2018  
 - [Weakly-supervised discovery of geometry-aware representation for 3d human pose estimation](https://openaccess.thecvf.com/content_CVPR_2019/papers/Chen_Weakly-Supervised_Discovery_of_Geometry-Aware_Representation_for_3D_Human_Pose_Estimation_CVPR_2019_paper.pdf) - CVPR 2019  
 - [Weakly-supervised 3d human pose learning via multi-view images in the wild](https://openaccess.thecvf.com/content_CVPR_2020/papers/Iqbal_Weakly-Supervised_3D_Human_Pose_Learning_via_Multi-View_Images_in_the_CVPR_2020_paper.pdf) - CVPR 2020  
 - [Self-supervised learning of 3d human pose using multi-view geometry](https://openaccess.thecvf.com/content_CVPR_2019/papers/Kocabas_Self-Supervised_Learning_of_3D_Human_Pose_Using_Multi-View_Geometry_CVPR_2019_paper.pdf) - CVPR 2019  
 - [Repnet: Weakly supervised training of an adversarial reprojection network for 3d human pose estimation](https://openaccess.thecvf.com/content_CVPR_2019/papers/Wandt_RepNet_Weakly_Supervised_Training_of_an_Adversarial_Reprojection_Network_for_CVPR_2019_paper.pdf) - CVPR 2019  
 - [Canonpose: Self-supervised monocular 3d human pose estimation in the wild](https://openaccess.thecvf.com/content/CVPR2021/papers/Wandt_CanonPose_Self-Supervised_Monocular_3D_Human_Pose_Estimation_in_the_Wild_CVPR_2021_paper.pdf) - CVPR 2021  
 - [Temporal hockey action recognition via pose and optical flows](https://openaccess.thecvf.com/content_CVPRW_2019/papers/CVSports/Cai_Temporal_Hockey_Action_Recognition_via_Pose_and_Optical_Flows_CVPRW_2019_paper.pdf) - CVPR Workshops 2019  
