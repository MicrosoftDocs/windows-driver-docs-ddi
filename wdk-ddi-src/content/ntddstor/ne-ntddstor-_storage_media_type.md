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
ms.keywords: ntddstor/MO_NFR_525, MO_NFR_525, DST_L, STK_9940, PC_5_RW, ntddstor/SYQUEST_EZ135, PSTORAGE_MEDIA_TYPE enumeration pointer [Storage Devices], QIC, ntddstor/IOMEGA_ZIP, PSTORAGE_MEDIA_TYPE, ntddstor/ADR_2, ntddstor/SYQUEST_SYJET, DDS_4mm, ntddstor/SONY_D2, ntddstor/MO_3_RW, ntddstor/STK_DATA_D3, LTO_Accelis, ntddstor/ADR_1, AME_8mm, STORAGE_MEDIA_TYPE, ntddstor/DVD_RW, ntddstor/VXATape_2, ntddstor/PHILIPS_12_WO, ntddstor/STK_9840, DVD_RAM, DVD_ROM, CLEANER_CARTRIDGE, ntddstor/PD_5_RW, ntddstor/MP2_8mm, ntddstor/QIC, MO_5_WO, ntddstor/CLEANER_CARTRIDGE, IBM_Magstar_3590, AVATAR_F2, ntddstor/CD_RW, ntddstor/DST_M, LTO_Ultrium, ntddstor/KODAK_14_WO, AIT1_8mm, ntddstor/CD_R, ntddstor/MO_5_WO, _STORAGE_MEDIA_TYPE, HITACHI_12_WO, ntddstor/STK_9940, ntddstor/VXATape_1, CD_RW, ABL_5_WO, ntddstor/STORAGE_MEDIA_TYPE, ntddstor/ABL_5_WO, ntddstor/NIKON_12_RW, ntddstor/AVATAR_F2, MO_5_RW, VXATape_2, storage.storage_media_type, ntddstor/DVD_R, CYGNET_12_WO, PHILIPS_12_WO, VXATape, ntddstor/MP_8mm, NCTP, IBM_Magstar_MP, IBM_3490E, SYQUEST_EZ135, ntddstor/DVD_RAM, STK_DATA_D3, ntddstor/IOMEGA_JAZ, SONY_D2, *PSTORAGE_MEDIA_TYPE, IBM_3480, ntddstor/Travan, ntddstor/AME_8mm, PD_5_RW, AIT_8mm, DVD_R, ntddstor/PC_5_WO, ntddstor/VXATape, SYQUEST_SYJET, ntddstor/IBM_3480, ntddstor/SAIT, MP_8mm, ntddstor/SYQUEST_EZFLYER, DVD_RW, DV_6mm, ntddstor/DVD_ROM, MiniQic, STORAGE_MEDIA_TYPE enumeration [Storage Devices], ntddstor/DST_S, ntddstor/DMI, CD_ROM, KODAK_14_WO, IOMEGA_ZIP, Travan, PC_5_WO, ntddstor/PINNACLE_APEX_5_RW, ntddstor/HITACHI_12_WO, SONY_DTF, IOMEGA_JAZ, ntddstor/LTO_Accelis, ntddstor/IBM_Magstar_3590, MP2_8mm, ntddstor/AIT_8mm, ntddstor/PC_5_RW, MO_5_LIMDOW, NIKON_12_RW, ADR_2, ntddstor/CYGNET_12_WO, ntddstor/MO_5_RW, ntddstor/PSTORAGE_MEDIA_TYPE, CD_R, ntddstor/LTO_Ultrium, ntddstor/DV_6mm, SYQUEST_EZFLYER, ntddstor/DDS_4mm, SONY_12_WO, ADR_1, ntddstor/SONY_12_WO, structs-general_d1e0e1bc-5ce9-49d0-9ab5-94b5e495d124.xml, ntddstor/AIT1_8mm, DST_S, ntddstor/SONY_DTF, SAIT, ntddstor/IBM_Magstar_MP, ntddstor/NCTP, DLT, ntddstor/CD_ROM, PINNACLE_APEX_5_RW, DMI, ntddstor/IBM_3490E, ntddstor/MO_5_LIMDOW, ntddstor/DLT, MO_3_RW, DST_M, STK_9840, ntddstor/MiniQic, ntddstor/DST_L, VXATape_1
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
req.typenames: STORAGE_MEDIA_TYPE, *PSTORAGE_MEDIA_TYPE
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




#### - DDS_4mm

Indicates a DAT DDS1 or DDS2 tape device (all vendors).


#### - MiniQic

Indicates a mini-QIC tape device. 


#### - Travan

Indicates a Travan TR-1, 2 or 3 tape device. 


#### - QIC

Indicates a QIC tape device. 


#### - MP_8mm

Indicates an 8mm Exabyte metal particle tape device. 


#### - AME_8mm

Indicates an 8mm Exabyte advanced metal tape device.


#### - AIT1_8mm

Indicates an 8mm Sony AIT tape device. 


#### - DLT

Indicates a DLT compact IIIxt or IV tape device. 


#### - NCTP

Indicates a Philips NCTP tape device. 


#### - IBM_3480

Indicates an IBM 3480 tape device. 


#### - IBM_3490E

Indicates an IBM 3490E tape device.


#### - IBM_Magstar_3590

Indicates an IBM Magstar 3590 tape device. 


#### - IBM_Magstar_MP

Indicates an IBM Magstar MP tape device. 


#### - STK_DATA_D3

Indicates an STK data D3 tape device. 


#### - SONY_DTF

Indicates a Sony DTF tape device. 


#### - DV_6mm

Indicates a 6mm digital video tape device. 


#### - DMI

Indicates a Exabyte DMI tape device and compatible devices. 


#### - SONY_D2

Indicates a Sony D2S or D2L tape device. 


#### - CLEANER_CARTRIDGE

Indicates a drive type that supports drive cleaners. 


#### - CD_ROM

Indicates a CD optical disk. 


#### - CD_R

Indicates a CD-recordable (write once) optical disk. 


#### - CD_RW

Indicates a CD-rewritable optical disk. 


#### - DVD_ROM

Indicates a DVD-ROM optical disk. 


#### - DVD_R

Indicates a DVD-recordable (write once) optical disk. 


#### - DVD_RW

Indicates a DVD-rewritable optical disk. 


#### - MO_3_RW

Indicates a 3.5" rewritable MO optical disk. 


#### - MO_5_WO

Indicates a MO 5.25" write once optical disk. 


#### - MO_5_RW

Indicates a MO 5.25" rewritable (not LIMDOW) optical disk.


#### - MO_5_LIMDOW

Indicates a MO 5.25" rewritable (LIMDOW) optical disk. 


#### - PC_5_WO

Indicates a phase change 5.25" write once optical disk. 


#### - PC_5_RW

Indicates a phase change 5.25" rewritable optical disk. 


#### - PD_5_RW

Indicates a phase change dual rewritable optical disk. 


#### - ABL_5_WO

Indicates a ablative 5.25" write once optical disk. 


#### - PINNACLE_APEX_5_RW

Indicates a pinnacle apex 4.6-GB rewritable optical disk.


#### - SONY_12_WO

Indicates a Sony 12" write once optical disk. 


#### - PHILIPS_12_WO

Indicates a Philips/LMS 12" write once optical disk. 


#### - HITACHI_12_WO

Indicates a Hitachi 12" write once optical disk. 


#### - CYGNET_12_WO

Indicates a Cygnet/ATG 12" write once optical disk. 


#### - KODAK_14_WO

Indicates a Kodak 14" write once optical disk. 


#### - MO_NFR_525

Indicates a near field recording (Terastor) optical disk. 


#### - NIKON_12_RW

Indicates a Nikon 12" rewritable optical disk. 


#### - IOMEGA_ZIP

Indicates Iomega zip magnetic disk device. 


#### - IOMEGA_JAZ

Indicates an Iomega Jaz magnetic disk device. 


#### - SYQUEST_EZ135

Indicates a Syquest EZ135 magnetic disk device. 


#### - SYQUEST_EZFLYER

Indicates a Syquest EzFlyer magnetic disk device. 


#### - SYQUEST_SYJET

Indicates a Syquest SyJet magnetic disk device. 


#### - AVATAR_F2

Indicates a 2.5" Floppy device. 


#### - MP2_8mm

Indicates an 8mm Hitachi tape device. 


#### - DST_S

Indicates a type DST Ampex small tape device. 


#### - DST_M

Indicates a type DST Ampex medium tape device. 


#### - DST_L

Indicates a type DST Ampex large tape device. 


#### - VXATape_1

Indicates an 8mm Ecrix tape device. 


#### - VXATape_2

Indicates an 8mm Ecrix tape device. 


### -field STK_EAGLE



#### - LTO_Ultrium

Indicates an IBM, HP, or Seagate LTO Ultrium device. 


#### - LTO_Accelis

Indicates an IBM, HP, or Seagate LTO Accelis


#### - DVD_RAM

Indicates a DVD-RAM optical device. 


#### - AIT_8mm

Indicates an AIT2 or higher 8mm tape device. 


#### - ADR_1

Indicates an on-stream ADR media type device. 


#### - ADR_2

Indicates an on-stream ADR media type device. 


#### - STK_9940

STK 9940


#### - SAIT

SAIT Tapes


#### - VXATape

VXA (Ecrix 8mm) Tape


#### - STK_9840

Indicates an STK 9840 device. 


## -see-also

<a href="..\ntddstor\ni-ntddstor-ioctl_storage_get_media_types_ex.md">IOCTL_STORAGE_GET_MEDIA_TYPES_EX</a>

<a href="..\ntddstor\ns-ntddstor-_get_media_types.md">GET_MEDIA_TYPES</a>

<a href="..\ntddstor\ns-ntddstor-_device_media_info.md">DEVICE_MEDIA_INFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STORAGE_MEDIA_TYPE enumeration%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

