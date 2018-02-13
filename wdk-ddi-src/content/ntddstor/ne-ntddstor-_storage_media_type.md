---
UID: NE:ntddstor._STORAGE_MEDIA_TYPE
title: "_STORAGE_MEDIA_TYPE"
author: windows-driver-content
description: The STORAGE_MEDIA_TYPE enumeration is used in conjunction with the IOCTL_STORAGE_GET_MEDIA_TYPES_EX request to query the class driver for the types of media that a device supports.
old-location: storage\storage_media_type.htm
old-project: storage
ms.assetid: 70214b6e-92d2-418a-ad8a-8701df02fdc3
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ntddstor/SYQUEST_EZFLYER, ntddstor/MO_5_WO, _STORAGE_MEDIA_TYPE, *PSTORAGE_MEDIA_TYPE, ntddstor/SAIT, CYGNET_12_WO, ntddstor/DVD_RAM, ntddstor/SYQUEST_SYJET, PD_5_RW, DMI, ntddstor/MO_5_RW, ntddstor/QIC, ntddstor/ADR_2, ntddstor/AVATAR_F2, ntddstor/IBM_Magstar_3590, IOMEGA_JAZ, NCTP, MO_5_LIMDOW, ntddstor/DST_L, ntddstor/ABL_5_WO, DVD_R, ntddstor/DST_M, DLT, ntddstor/STK_9840, MiniQic, ntddstor/KODAK_14_WO, ntddstor/PSTORAGE_MEDIA_TYPE, ntddstor/IBM_3480, MO_5_WO, ntddstor/CLEANER_CARTRIDGE, PC_5_RW, MO_3_RW, IBM_Magstar_3590, ntddstor/CD_R, ntddstor/AIT1_8mm, STK_DATA_D3, ntddstor/DDS_4mm, ntddstor/DVD_ROM, NIKON_12_RW, ntddstor/ADR_1, ntddstor/STORAGE_MEDIA_TYPE, SONY_DTF, ntddstor/Travan, MP2_8mm, QIC, CD_R, SONY_12_WO, DST_M, VXATape_2, KODAK_14_WO, DVD_RAM, MP_8mm, DVD_RW, IBM_Magstar_MP, AME_8mm, DST_S, SAIT, ntddstor/MiniQic, ntddstor/DVD_RW, ntddstor/PC_5_WO, IOMEGA_ZIP, ABL_5_WO, STK_9840, DST_L, ntddstor/PINNACLE_APEX_5_RW, DDS_4mm, ntddstor/CYGNET_12_WO, ntddstor/MO_NFR_525, LTO_Accelis, DV_6mm, ntddstor/NCTP, ntddstor/VXATape_2, SYQUEST_EZFLYER, storage.storage_media_type, ntddstor/IBM_3490E, PINNACLE_APEX_5_RW, SYQUEST_EZ135, CD_RW, ntddstor/DST_S, STORAGE_MEDIA_TYPE enumeration [Storage Devices], ntddstor/VXATape_1, VXATape_1, ntddstor/LTO_Ultrium, STK_9940, CLEANER_CARTRIDGE, SYQUEST_SYJET, ntddstor/MO_5_LIMDOW, ntddstor/STK_9940, PHILIPS_12_WO, STORAGE_MEDIA_TYPE, ntddstor/MP_8mm, VXATape, DVD_ROM, ntddstor/SYQUEST_EZ135, AIT_8mm, ntddstor/PHILIPS_12_WO, ntddstor/MP2_8mm, LTO_Ultrium, ntddstor/AME_8mm, ntddstor/MO_3_RW, ntddstor/IBM_Magstar_MP, CD_ROM, ntddstor/DV_6mm, MO_NFR_525, SONY_D2, AIT1_8mm, ntddstor/STK_DATA_D3, ntddstor/IOMEGA_JAZ, MO_5_RW, ntddstor/IOMEGA_ZIP, AVATAR_F2, ntddstor/HITACHI_12_WO, ntddstor/SONY_12_WO, ntddstor/PD_5_RW, IBM_3490E, ntddstor/DVD_R, PSTORAGE_MEDIA_TYPE, ntddstor/LTO_Accelis, ntddstor/VXATape, HITACHI_12_WO, ntddstor/DLT, ntddstor/CD_ROM, ntddstor/CD_RW, PC_5_WO, ntddstor/SONY_DTF, ntddstor/DMI, ntddstor/NIKON_12_RW, PSTORAGE_MEDIA_TYPE enumeration pointer [Storage Devices], ADR_1, ntddstor/AIT_8mm, ADR_2, structs-general_d1e0e1bc-5ce9-49d0-9ab5-94b5e495d124.xml, Travan, ntddstor/PC_5_RW, IBM_3480, ntddstor/SONY_D2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddstor.h
apiname:
-	STORAGE_MEDIA_TYPE
product: Windows
targetos: Windows
req.typenames: "*PSTORAGE_MEDIA_TYPE, STORAGE_MEDIA_TYPE"
---

# _STORAGE_MEDIA_TYPE enumeration


## -description


The STORAGE_MEDIA_TYPE enumeration is used in conjunction with the <a href="..\ntddstor\ni-ntddstor-ioctl_storage_get_media_types_ex.md">IOCTL_STORAGE_GET_MEDIA_TYPES_EX</a> request to query the class driver for the types of media that a device supports.


## -syntax


````
typedef enum _STORAGE_MEDIA_TYPE { 
  DDS_4mm             = 0x20,
  MiniQic             = 0x21,
  Travan              = 0x22,
  QIC                 = 0x23,
  MP_8mm              = 0x24,
  AME_8mm             = 0x25,
  AIT1_8mm            = 0x26,
  DLT                 = 0x27,
  NCTP                = 0x28,
  IBM_3480            = 0x29,
  IBM_3490E           = 0x2A,
  IBM_Magstar_3590    = 0x2B,
  IBM_Magstar_MP      = 0x2C,
  STK_DATA_D3         = 0x2D,
  SONY_DTF            = 0x2E,
  DV_6mm              = 0x2F,
  DMI                 = 0x30,
  SONY_D2             = 0x31,
  CLEANER_CARTRIDGE   = 0x32,
  CD_ROM              = 0x33,
  CD_R                = 0x34,
  CD_RW               = 0x35,
  DVD_ROM             = 0x36,
  DVD_R               = 0x37,
  DVD_RW              = 0x38,
  MO_3_RW             = 0x39,
  MO_5_WO             = 0x3A,
  MO_5_RW             = 0x3B,
  MO_5_LIMDOW         = 0x3C,
  PC_5_WO             = 0x3D,
  PC_5_RW             = 0x3E,
  PD_5_RW             = 0x3F,
  ABL_5_WO            = 0x40,
  PINNACLE_APEX_5_RW  = 0x41,
  SONY_12_WO          = 0x42,
  PHILIPS_12_WO       = 0x43,
  HITACHI_12_WO       = 0x44,
  CYGNET_12_WO        = 0x45,
  KODAK_14_WO         = 0x46,
  MO_NFR_525          = 0x47,
  NIKON_12_RW         = 0x48,
  IOMEGA_ZIP          = 0x49,
  IOMEGA_JAZ          = 0x4A,
  SYQUEST_EZ135       = 0x4B,
  SYQUEST_EZFLYER     = 0x4C,
  SYQUEST_SYJET       = 0x4D,
  AVATAR_F2           = 0x4E,
  MP2_8mm             = 0x4F,
  DST_S               = 0x50,
  DST_M               = 0x51,
  DST_L               = 0x52,
  VXATape_1           = 0x53,
  VXATape_2           = 0x54,
  STK_9840            = 0x55,
  LTO_Ultrium         = 0x56,
  LTO_Accelis         = 0x57,
  DVD_RAM             = 0x58,
  AIT_8mm             = 0x59,
  ADR_1               = 0x5A,
  ADR_2               = 0x5B,
  STK_9940            = 0x5C,
  SAIT                = 0x5D,
  VXATape             = 0x5E
} STORAGE_MEDIA_TYPE, *PSTORAGE_MEDIA_TYPE;
````


## -enum-fields




### -field DDS_4mm

Indicates a DAT DDS1 or DDS2 tape device (all vendors).


### -field MiniQic

Indicates a mini-QIC tape device. 


### -field Travan

Indicates a Travan TR-1, 2 or 3 tape device. 


### -field QIC

Indicates a QIC tape device. 


### -field MP_8mm

Indicates an 8mm Exabyte metal particle tape device. 


### -field AME_8mm

Indicates an 8mm Exabyte advanced metal tape device.


### -field AIT1_8mm

Indicates an 8mm Sony AIT tape device. 


### -field DLT

Indicates a DLT compact IIIxt or IV tape device. 


### -field NCTP

Indicates a Philips NCTP tape device. 


### -field IBM_3480

Indicates an IBM 3480 tape device. 


### -field IBM_3490E

Indicates an IBM 3490E tape device.


### -field IBM_Magstar_3590

Indicates an IBM Magstar 3590 tape device. 


### -field IBM_Magstar_MP

Indicates an IBM Magstar MP tape device. 


### -field STK_DATA_D3

Indicates an STK data D3 tape device. 


### -field SONY_DTF

Indicates a Sony DTF tape device. 


### -field DV_6mm

Indicates a 6mm digital video tape device. 


### -field DMI

Indicates a Exabyte DMI tape device and compatible devices. 


### -field SONY_D2

Indicates a Sony D2S or D2L tape device. 


### -field CLEANER_CARTRIDGE

Indicates a drive type that supports drive cleaners. 


### -field CD_ROM

Indicates a CD optical disk. 


### -field CD_R

Indicates a CD-recordable (write once) optical disk. 


### -field CD_RW

Indicates a CD-rewritable optical disk. 


### -field DVD_ROM

Indicates a DVD-ROM optical disk. 


### -field DVD_R

Indicates a DVD-recordable (write once) optical disk. 


### -field DVD_RW

Indicates a DVD-rewritable optical disk. 


### -field MO_3_RW

Indicates a 3.5" rewritable MO optical disk. 


### -field MO_5_WO

Indicates a MO 5.25" write once optical disk. 


### -field MO_5_RW

Indicates a MO 5.25" rewritable (not LIMDOW) optical disk.


### -field MO_5_LIMDOW

Indicates a MO 5.25" rewritable (LIMDOW) optical disk. 


### -field PC_5_WO

Indicates a phase change 5.25" write once optical disk. 


### -field PC_5_RW

Indicates a phase change 5.25" rewritable optical disk. 


### -field PD_5_RW

Indicates a phase change dual rewritable optical disk. 


### -field ABL_5_WO

Indicates a ablative 5.25" write once optical disk. 


### -field PINNACLE_APEX_5_RW

Indicates a pinnacle apex 4.6-GB rewritable optical disk.


### -field SONY_12_WO

Indicates a Sony 12" write once optical disk. 


### -field PHILIPS_12_WO

Indicates a Philips/LMS 12" write once optical disk. 


### -field HITACHI_12_WO

Indicates a Hitachi 12" write once optical disk. 


### -field CYGNET_12_WO

Indicates a Cygnet/ATG 12" write once optical disk. 


### -field KODAK_14_WO

Indicates a Kodak 14" write once optical disk. 


### -field MO_NFR_525

Indicates a near field recording (Terastor) optical disk. 


### -field NIKON_12_RW

Indicates a Nikon 12" rewritable optical disk. 


### -field IOMEGA_ZIP

Indicates Iomega zip magnetic disk device. 


### -field IOMEGA_JAZ

Indicates an Iomega Jaz magnetic disk device. 


### -field SYQUEST_EZ135

Indicates a Syquest EZ135 magnetic disk device. 


### -field SYQUEST_EZFLYER

Indicates a Syquest EzFlyer magnetic disk device. 


### -field SYQUEST_SYJET

Indicates a Syquest SyJet magnetic disk device. 


### -field AVATAR_F2

Indicates a 2.5" Floppy device. 


### -field MP2_8mm

Indicates an 8mm Hitachi tape device. 


### -field DST_S

Indicates a type DST Ampex small tape device. 


### -field DST_M

Indicates a type DST Ampex medium tape device. 


### -field DST_L

Indicates a type DST Ampex large tape device. 


### -field VXATape_1

Indicates an 8mm Ecrix tape device. 


### -field VXATape_2

Indicates an 8mm Ecrix tape device. 


### -field STK_EAGLE


### -field LTO_Ultrium

Indicates an IBM, HP, or Seagate LTO Ultrium device. 


### -field LTO_Accelis

Indicates an IBM, HP, or Seagate LTO Accelis


### -field DVD_RAM

Indicates a DVD-RAM optical device. 


### -field AIT_8mm

Indicates an AIT2 or higher 8mm tape device. 


### -field ADR_1

Indicates an on-stream ADR media type device. 


### -field ADR_2

Indicates an on-stream ADR media type device. 


### -field STK_9940

STK 9940


### -field SAIT

SAIT Tapes


### -field VXATape

VXA (Ecrix 8mm) Tape


#### - STK_9840

Indicates an STK 9840 device. 


## -see-also

<a href="..\ntddstor\ns-ntddstor-_get_media_types.md">GET_MEDIA_TYPES</a>



<a href="..\ntddstor\ni-ntddstor-ioctl_storage_get_media_types_ex.md">IOCTL_STORAGE_GET_MEDIA_TYPES_EX</a>



<a href="..\ntddstor\ns-ntddstor-_device_media_info.md">DEVICE_MEDIA_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STORAGE_MEDIA_TYPE enumeration%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

