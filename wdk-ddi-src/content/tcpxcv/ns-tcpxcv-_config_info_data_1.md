---
UID: NS:tcpxcv._CONFIG_INFO_DATA_1
title: "_CONFIG_INFO_DATA_1"
author: windows-driver-content
description: The XcvData function uses a CONFIG_INFO_DATA_1 structure when it obtains configuration data for a particular port.
old-location: print\config_info_data_1.htm
old-project: print
ms.assetid: abf484e4-6a11-4727-b195-5eaf6683113e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PCONFIG_INFO_DATA_1, CONFIG_INFO_DATA_1, CONFIG_INFO_DATA_1 structure [Print Devices], PCONFIG_INFO_DATA_1, PCONFIG_INFO_DATA_1 structure pointer [Print Devices], _CONFIG_INFO_DATA_1, print.config_info_data_1, spoolfnc_b18027cc-7df5-452c-81cd-b62bfa5395f3.xml, tcpxcv/CONFIG_INFO_DATA_1, tcpxcv/PCONFIG_INFO_DATA_1"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: tcpxcv.h
req.include-header: Tcpxcv.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	tcpxcv.h
api_name:
-	CONFIG_INFO_DATA_1
product:
- Windows
targetos: Windows
req.typenames: CONFIG_INFO_DATA_1, *PCONFIG_INFO_DATA_1
req.product: Windows 10 or later.
---

# _CONFIG_INFO_DATA_1 structure


## -description


The <a href="https://msdn.microsoft.com/library/windows/hardware/ff564255">XcvData</a> function uses a CONFIG_INFO_DATA_1 structure when it obtains configuration data for a particular port.


## -struct-fields




### -field Reserved

Is reserved for system use. This member should be set to a zero-length string.


### -field dwVersion

Specifies the version of the PORT_DATA_1 structure (currently equal to 1) that will contain the configuration information.


## -remarks



When the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564255">XcvData</a> function is called to obtain port configuration information, its <i>pInputData</i> parameter must be set with the address of a CONFIG_INFO_DATA_1 structure, and its <i>pOutputData</i> parameter must be set with the address of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff559892">PORT_DATA_1</a> structure, which will be filled in when the function returns. Set this function's <i>pszDataName</i> parameter to the string L"GetConfigInfo". 

See <a href="https://msdn.microsoft.com/7b2b1cff-ab8f-44e0-9327-dc60a0072bf5">TCPMON Xcv Interface</a> for more information.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559892">PORT_DATA_1</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564255">XcvData</a>
 

 

