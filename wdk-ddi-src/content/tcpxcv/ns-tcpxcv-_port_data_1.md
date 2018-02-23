---
UID: NS:tcpxcv._PORT_DATA_1
title: "_PORT_DATA_1"
author: windows-driver-content
description: The XcvData function uses a PORT_DATA_1 structure when it adds a port or configures an existing port.
old-location: print\port_data_1.htm
old-project: print
ms.assetid: 6d2165a7-ee21-4f7d-a03c-f9bed87a3c7a
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: spoolfnc_6fd52423-d2f1-4c6c-bf42-63000c5d0e66.xml, _PORT_DATA_1, print.port_data_1, *PPORT_DATA_1, PORT_DATA_1 structure [Print Devices], PPORT_DATA_1 structure pointer [Print Devices], PPORT_DATA_1, PORT_DATA_1, tcpxcv/PORT_DATA_1, tcpxcv/PPORT_DATA_1
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
-	PORT_DATA_1
product: Windows
targetos: Windows
req.typenames: PORT_DATA_1, *PPORT_DATA_1
req.product: Windows 10 or later.
---

# _PORT_DATA_1 structure


## -description


The <a href="https://msdn.microsoft.com/library/windows/hardware/ff564255">XcvData</a> function uses a PORT_DATA_1 structure when it adds a port or configures an existing port.


## -syntax


````
typedef struct _PORT_DATA_1 {
  WCHAR sztPortName[MAX_PORTNAME_LEN];
  DWORD dwVersion;
  DWORD dwProtocol;
  DWORD cbSize;
  DWORD dwReserved;
  WCHAR sztHostAddress[MAX_NETWORKNAME_LEN];
  WCHAR sztSNMPCommunity[MAX_SNMP_COMMUNITY_STR_LEN];
  DWORD dwDoubleSpool;
  WCHAR sztQueue[MAX_QUEUENAME_LEN];
  WCHAR sztIPAddress[MAX_IPADDR_STR_LEN];
  BYTE  Reserved[540];
  DWORD dwPortNumber;
  DWORD dwSNMPEnabled;
  DWORD dwSNMPDevIndex;
} PORT_DATA_1, *PPORT_DATA_1;
````


## -struct-fields




### -field sztPortName

Specifies the name of the port. The MAX_PORTNAME_LEN constant is defined in tcpxcv.h.


### -field dwVersion

Specifies the version number of the PORT_DATA_1 structure, which is currently 1.


### -field dwProtocol

Specifies the protocol to use for the port. This value can be either PROTOCOL_RAWTCP_TYPE or PROTOCOL_LPR_TYPE, constants that are defined in tcpxcv.h.


### -field cbSize

Specifies the size, in bytes of this structure. Use <b>sizeof</b>(PORT_DATA_1) for this value.


### -field dwReserved

Reserved, must be set to zero.


### -field sztHostAddress

Specifies the IP Address or host name of the printer. The MAX_NETWORKNAME_LEN constant is defined in tcpxcv.h.


### -field sztSNMPCommunity

Specifies the SNMP community name of the printer. The MAX_SNMP_COMMUNITY_STR_LEN constant is defined in tcpxcv.h.


### -field dwDoubleSpool

If <b>TRUE</b>, indicates that double spooling is enabled. If <b>FALSE</b>, double spooling is disabled.


### -field sztQueue

Specifies the LPR queue name. The MAX_QUEUENAME_LEN constant is defined in tcpxcv.h.


### -field sztIPAddress

Specifies the IP address of the printer. The MAX_IPADDR_STR_LEN constant is defined in tcpxcv.h.


### -field Reserved

Reserved, must be set to zero.


### -field dwPortNumber

Specifies the port number of the device.


### -field dwSNMPEnabled

If <b>TRUE</b>, indicates that the device supports Simple Network Management Protocol (SNMP).


### -field dwSNMPDevIndex

Specifies the SNMP device index.


## -remarks



When the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564255">XcvData</a> function is called either to add a port or configure an existing port, its <i>pOutputData</i> parameter must be set with the address of a PORT_DATA_1 structure, which will be filled in when the function returns. To add a port, set this function's <i>pszDataName</i> parameter to the string L"AddPort". To configure a port, set this parameter to L"ConfigPort". 

See <a href="https://msdn.microsoft.com/7b2b1cff-ab8f-44e0-9327-dc60a0072bf5">TCPMON Xcv Interface</a> for more information.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564255">XcvData</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20PORT_DATA_1 structure%20 RELEASE:%20(2/21/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

