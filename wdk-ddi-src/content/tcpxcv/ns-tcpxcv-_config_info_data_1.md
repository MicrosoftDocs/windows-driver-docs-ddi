---
UID: NS:tcpxcv._CONFIG_INFO_DATA_1
title: "_CONFIG_INFO_DATA_1"
author: windows-driver-content
description: The XcvData function uses a CONFIG_INFO_DATA_1 structure when it obtains configuration data for a particular port.
old-location: print\config_info_data_1.htm
old-project: print
ms.assetid: abf484e4-6a11-4727-b195-5eaf6683113e
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: PCONFIG_INFO_DATA_1 structure pointer [Print Devices], tcpxcv/CONFIG_INFO_DATA_1, spoolfnc_b18027cc-7df5-452c-81cd-b62bfa5395f3.xml, tcpxcv/PCONFIG_INFO_DATA_1, *PCONFIG_INFO_DATA_1, CONFIG_INFO_DATA_1, PCONFIG_INFO_DATA_1, _CONFIG_INFO_DATA_1, print.config_info_data_1, CONFIG_INFO_DATA_1 structure [Print Devices]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	tcpxcv.h
apiname:
-	CONFIG_INFO_DATA_1
product: Windows
targetos: Windows
req.typenames: "*PCONFIG_INFO_DATA_1, CONFIG_INFO_DATA_1"
req.product: Windows 10 or later.
---

# _CONFIG_INFO_DATA_1 structure


## -description


The <a href="https://msdn.microsoft.com/library/windows/hardware/ff564255">XcvData</a> function uses a CONFIG_INFO_DATA_1 structure when it obtains configuration data for a particular port.


## -syntax


````
typedef struct _CONFIG_INFO_DATA_1 {
  BYTE  Reserved[128];
  DWORD dwVersion;
} CONFIG_INFO_DATA_1, *PCONFIG_INFO_DATA_1;
````


## -struct-fields




### -field Reserved

Is reserved for system use. This member should be set to a zero-length string.


### -field dwVersion

Specifies the version of the PORT_DATA_1 structure (currently equal to 1) that will contain the configuration information.


## -remarks



When the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564255">XcvData</a> function is called to obtain port configuration information, its <i>pInputData</i> parameter must be set with the address of a CONFIG_INFO_DATA_1 structure, and its <i>pOutputData</i> parameter must be set with the address of a <a href="..\tcpxcv\ns-tcpxcv-_port_data_1.md">PORT_DATA_1</a> structure, which will be filled in when the function returns. Set this function's <i>pszDataName</i> parameter to the string L"GetConfigInfo". 

See <a href="https://msdn.microsoft.com/7b2b1cff-ab8f-44e0-9327-dc60a0072bf5">TCPMON Xcv Interface</a> for more information.




## -see-also

<a href="..\tcpxcv\ns-tcpxcv-_port_data_1.md">PORT_DATA_1</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564255">XcvData</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20CONFIG_INFO_DATA_1 structure%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

