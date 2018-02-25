---
UID: NS:pep_x._PEP_PPM_QUERY_LP_SETTINGS
title: "_PEP_PPM_QUERY_LP_SETTINGS"
author: windows-driver-content
description: The PEP_PPM_QUERY_LP_SETTINGS structure contains a kernel handle to the registry key that contains the power optimization settings that the platform extension plug-in (PEP) has defined for each power scenario.
old-location: kernel\pep_ppm_query_lp_settings.htm
old-project: kernel
ms.assetid: 69A8792B-954E-49AF-A306-25B94183E58A
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PPEP_PPM_QUERY_LP_SETTINGS, ,, E, G, I, L, M, N, P, PEP_PPM_QUERY_LP_SETTINGS, PEP_PPM_QUERY_LP_SETTINGS structure [Kernel-Mode Driver Architecture], PPEP_PPM_QUERY_LP_SETTINGS, PPEP_PPM_QUERY_LP_SETTINGS structure pointer [Kernel-Mode Driver Architecture], Q, R, S, T, U, Y, _, _PEP_PPM_QUERY_LP_SETTINGS, kernel.pep_ppm_query_lp_settings, pep_x/PEP_PPM_QUERY_LP_SETTINGS, pep_x/PPEP_PPM_QUERY_LP_SETTINGS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pep_x.h
req.include-header: Pepfx.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pep_x.h
apiname:
-	PEP_PPM_QUERY_LP_SETTINGS
product: Windows
targetos: Windows
req.typenames: PEP_PPM_QUERY_LP_SETTINGS, *PPEP_PPM_QUERY_LP_SETTINGS
---

# _PEP_PPM_QUERY_LP_SETTINGS structure


## -description


The <b>PEP_PPM_QUERY_LP_SETTINGS</b> structure contains a kernel handle to the registry key that contains the power optimization settings that the platform extension plug-in (PEP) has defined for each power scenario.


## -syntax


````
typedef struct _PEP_PPM_QUERY_LP_SETTINGS {
  HANDLE RegistryRoot;
} PEP_PPM_QUERY_LP_SETTINGS, *PPEP_PPM_QUERY_LP_SETTINGS;
````


## -struct-fields




### -field RegistryRoot

[out] The kernel handle to the registry root that contains the settings for a platform power scenario. For more information, see Remarks.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt629122">PEP_NOTIFY_PPM_QUERY_LP_SETTINGS</a> notification. The <b>RegistryRoot</b> member contains an output value that the PEP writes to the structure in response to this notification.

The PEP can provide settings for certain key power scenarios such as full-screen video playback and connected standby that have unique characteristics that can benefit from specially tuned power policies that are different from the default settings used by Windows. The PEP loads the settings for such a power scenario into the registry and passes the registry key for these settings to the operating system. 




## -see-also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt629122">PEP_NOTIFY_PPM_QUERY_LP_SETTINGS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PPM_QUERY_LP_SETTINGS structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

