---
UID: NS:bthioctl._BTH_RADIO_INFO
title: "_BTH_RADIO_INFO"
author: windows-driver-content
description: The BTH_RADIO_INFO structure contains information about a remote radio.
old-location: bltooth\bth_radio_info.htm
old-project: bltooth
ms.assetid: 24e28912-13d1-460f-8d32-78bb3715adc6
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: bth_structs_5fa8e736-47a7-4ba5-bd40-f375ac6db8af.xml, bthioctl/PBTH_RADIO_INFO, BTH_RADIO_INFO structure [Bluetooth Devices], bthioctl/BTH_RADIO_INFO, *PBTH_RADIO_INFO, PBTH_RADIO_INFO structure pointer [Bluetooth Devices], _BTH_RADIO_INFO, bltooth.bth_radio_info, PBTH_RADIO_INFO, BTH_RADIO_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bthioctl.h
req.include-header: Bthioctl.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
req.irql: "<= PASSIVE_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	bthioctl.h
apiname:
-	BTH_RADIO_INFO
product: Windows
targetos: Windows
req.typenames: "*PBTH_RADIO_INFO, BTH_RADIO_INFO"
---

# _BTH_RADIO_INFO structure


## -description


The BTH_RADIO_INFO structure contains information about a remote radio.


## -syntax


````
typedef struct _BTH_RADIO_INFO {
  ULONGLONG lmpSupportedFeatures;
  USHORT    mfg;
  USHORT    lmpSubversion;
  UCHAR     lmpVersion;
} BTH_RADIO_INFO, *PBTH_RADIO_INFO;
````


## -struct-fields




#### - lmpSupportedFeatures

A bitmap of Link Management Protocol (LMP) features that are supported by the local radio.


#### - mfg

The identification of the manufacturer.


#### - lmpSubversion

The minor version number for the LMP that is used by the local radio.


#### - lmpVersion

The major version number for the LMP that is used by the local radio.


## -remarks


The BTH_RADIO_INFO structure is returned as part of the output buffer of 
    <a href="..\bthioctl\ni-bthioctl-ioctl_bth_get_local_info.md">IOCTL_BTH_GET_LOCAL_INFO</a>. The local
    radio information is returned in the 
    <b>radioInfo</b> member of the 
    <a href="..\bthioctl\ns-bthioctl-_bth_local_radio_info.md">BTH_LOCAL_RADIO_INFO</a> structure.



## -see-also

<a href="..\bthioctl\ns-bthioctl-_bth_local_radio_info.md">BTH_LOCAL_RADIO_INFO</a>

<a href="..\bthioctl\ni-bthioctl-ioctl_bth_get_local_info.md">IOCTL_BTH_GET_LOCAL_INFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20BTH_RADIO_INFO structure%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

