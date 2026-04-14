---
title: "Coverages for Member-based Products"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_coverages_for_member-based_products.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Coverages for Member-based Products

Coverages for Member-based Products[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Coverages for Member-based Products

The spec that models a coverage provided as part of an insurance or health product. The coverage spec defines the required and optional coverages on an insurance product.

The member-based product has the coverage specs:

Medical Products
| Product Name | Product Code | Coverage Name | Coverage Code | Is Optional |
| --- | --- | --- | --- | --- |
| Medical Basic | MedicalBasic | Cost Coverage Medical | medCostCov | Required |
| Health Fund Info | medHealthFund | Optional |
| Medical Silver | MedicalSilver | Cost Coverage Medical | medCostCov | Required |
| Health Fund Info | medHealthFund | Optional |
| Prescription Coverage | Prescription Coverage | Optional |
| Medical Gold | MedicalGold | Cost Coverage Medical | medCostCov | Required |
| Deductibles and Maximums | medDedMax | Optional |
| Health Fund Info | medHealthFund | Optional |
| Prescription Coverage | medPresCov | Optional |
| Medical Diamond | MedicalDiamond | Cost Coverage Medical | medCostCov | Required |
| Deductibles and Maximums | medDedMax | Optional |
| Health Fund Info | medHealthFund | Optional |
| Prescription Coverage | medPresCov | Optional |
| Annual Health Checkup | AnnualHealthCheckup | Optional |
| Medical Platinum | MedicalPlatinum | Cost Coverage Medical | medCostCov | Required |
| Deductibles and Maximums | medDedMax | Optional |
| Deductibles and Maximums | medHealthFund | Optional |
| Prescription Coverage | medPresCov | Optional |
| Annual Health Checkup | AnnualHealthCheckup | Optional |
| MaternityCare | MaternityCare | Optional |

Dental Products
| Product Name | Product Code | Coverage Name | Coverage Code | Is Optional |
| --- | --- | --- | --- | --- |
| Dental Basic | DentalBasic | Dental Base Benefits | dentalBaseBenefits | Required |
| Deductibles & Maximums | dentalDedMax | Optional |
| Dental Silver | DentalSilver | Dental Base Benefits | dentalBaseBenefits | Required |
| Deductibles & Maximums | dentalDedMax | Optional |
| Orthodontia | dentalOrthodontia | Optional |
| Dental Gold | DentalGold | Dental Base Benefits | dentalBaseBenefits | Required |
| Deductibles & Maximums | dentalDedMax | Optional |
| Orthodontia | dentalOrthodontia | Optional |
| Implants | dentalImpants | Optional |
| Dental Diamond | DentalDiamond | Dental Base Benefits | dentalBaseBenefits | Required |
| Deductibles & Maximums | dentalDedMax | Optional |
| Orthodontia | dentalOrthodontia | Optional |
| Implants | dentalImpants | Optional |
| Dentures & Aligners | DenturesAligners | Optional |
| Dental Platinum | DentalPlatinum | Dental Base Benefits | dentalBaseBenefits | Required |
| Deductibles & Maximums | dentalDedMax | Optional |
| Orthodontia | dentalOrthodontia | Optional |
| Implants | dentalImpants | Optional |
| Dentures & Aligners | DenturesAligners | Optional |
| Extended Care | dentalExtendedCare | Optional |

Vision Products
| Product Code | Product Name | Coverage Name | Coverage Code | Is Optional |
| --- | --- | --- | --- | --- |
| Vision Basic | VisionBasic | Routine Eye Exam | visionRoutineEyeExam | Required |
| Lenses | visionLenses | Optional |
| Vision Silver | VisionSilver | Routine Eye Exam | visionRoutineEyeExam | Required |
| Lenses | visionLenses | Optional |
| Frames | visionFrames | Optional |
| Vision Gold | VisionGold | Routine Eye Exam | visionRoutineEyeExam | Required |
| Lenses | visionLenses | Optional |
| Frames | visionFrames | Optional |
| Contact Lenses | visionContactLenses | Optional |
| Vision Diamond | VisionDiamond | Routine Eye Exam | visionRoutineEyeExam | Required |
| Lenses | visionLenses | Optional |
| Frames | visionFrames | Optional |
| Contact Lenses | visionContactLenses | Optional |
| Eye Surgery | EyeSurgery | Optional |
| Vision Platinum | VisionPlatinum | Routine Eye Exam | visionRoutineEyeExam | Required |
| Lenses | visionLenses | Optional |
| Frames | visionFrames | Optional |
| Contact Lenses | visionContactLenses | Optional |
| Eye Surgery | EyeSurgery | Optional |
| LASIK | LASIK | Optional |

Critical Illness
| Product Name | Product Code | Coverage Name | Coverage Code | Is Optional |
| --- | --- | --- | --- | --- |
| Critical Illness Basic | CriticalIllnessBasic | Critical Illness Base Benefits | ciBaseBenefits | Required |
| Wellness/Health Screening | ciWellnessScreen | Optional |
| Critical Illness Silver | CriticalIllnessSilver | Critical Illness Base Benefits | ciBaseBenefits | Required |
| Wellness/Health Screening | ciWellnessScreen | Optional |
| Transitional Care Benefits | ciTransCareBenefits | Optional |
| Critical Illness Gold | CriticalIllnessGold | Critical Illness Base Benefits | ciBaseBenefits | Required |
| Wellness/Health Screening | ciWellnessScreen | Optional |
| Transitional Care Benefits | ciTransCareBenefits | Optional |
| Neurological Benefits | ciNeuroBenefits | Optional |
| Critical Illness Diamond | CriticalIllnessDiamond | Critical Illness Base Benefits | ciBaseBenefits | Required |
| Wellness/Health Screening | ciWellnessScreen | Optional |
| Transitional Care Benefits | ciTransCareBenefits | Optional |
| Neurological Benefits | ciNeuroBenefits | Optional |
| Travel Benefits Package | ciTravelBenefits | Optional |
| Critical Illness Platinum | CriticalIllnessPlatinum | Critical Illness Base Benefits | ciBaseBenefits | Required |
| Wellness/Health Screening | ciWellnessScreen | Optional |
| Transitional Care Benefits | ciTransCareBenefits | Optional |
| Neurological Benefits | ciNeuroBenefits | Optional |
| Travel Benefits Package | ciTravelBenefits | Optional |
| Extended Cancer | ciExtendedCancer | Optional |

Did this article solve your issue?

Let us know so we can improve!

YesNo