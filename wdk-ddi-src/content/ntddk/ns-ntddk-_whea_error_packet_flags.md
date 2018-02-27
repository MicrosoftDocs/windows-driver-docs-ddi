---
UID: NS:ntddk._WHEA_ERROR_PACKET_FLAGS
title: "_WHEA_ERROR_PACKET_FLAGS"
author: windows-driver-content
description: The WHEA_ERROR_PACKET_FLAGS union defines the error condition reported through a WHEA_ERROR_PACKET structure.
old-location: whea\whea_error_packet_flags.htm
old-project: whea
ms.assetid: e1dae7df-7d81-42cc-9a01-44345f53ba4e
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "*PWHEA_ERROR_PACKET_FLAGS, PWHEA_ERROR_PACKET_FLAGS, PWHEA_ERROR_PACKET_FLAGS union pointer [WHEA Drivers and Applications], WHEA_ERROR_PACKET_FLAGS, WHEA_ERROR_PACKET_FLAGS union [WHEA Drivers and Applications], _WHEA_ERROR_PACKET_FLAGS, ntddk/PWHEA_ERROR_PACKET_FLAGS, ntddk/WHEA_ERROR_PACKET_FLAGS, whea.whea_error_packet_flags, whearef_c193e4e7-f233-4de0-93ac-5e7b841a6c6e.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
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
-	ntddk.h
apiname:
-	WHEA_ERROR_PACKET_FLAGS
product: Windows
targetos: Windows
req.typenames: WHEA_ERROR_PACKET_FLAGS, *PWHEA_ERROR_PACKET_FLAGS
---

# _WHEA_ERROR_PACKET_FLAGS structure


## -description


The WHEA_ERROR_PACKET_FLAGS union defines the error condition reported through a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560465">WHEA_ERROR_PACKET</a> structure.


## -syntax


````
typedef union _WHEA_ERROR_PACKET_FLAGS {
  struct {
    ULONG PreviousError  :1;
    ULONG Reserved1  :1;
    ULONG HypervisorError  :1;
    ULONG Simulated  :1;
    ULONG PlatformPfaControl  :1;
    ULONG PlatformDirectedOffline  :1;
    ULONG Reserved2  :26;
  };
  ULONG  AsULONG;
} WHEA_ERROR_PACKET_FLAGS, *PWHEA_ERROR_PACKET_FLAGS;
````


## -struct-fields




### -field DUMMYSTRUCTNAME

 


### -field AsULONG

A ULONG representation of the contents of the WHEA_ERROR_PACKET_FLAGS union.


#### - HypervisorError

A single bit that indicates that a hypervisor error has occurred.


#### - PlatformDirectedOffline

A single bit that indicates whether the PSHED plug-in that performs PFA on a system component has determined if the component should be brought into an offline state. This bit is only valid if the <b>PlatformPfaControl</b> member is set.


<div class="alert"><b>Note</b>  This member is supported in Windows 7 and later versions of Windows.</div>
<div> </div>



#### - PlatformPfaControl

A single bit that indicates whether WHEA or a PSHED plug-in is in control of predictive failure analysis (PFA). If this bit is set, the PSHED plug-in is in control of PFA and must set the <b>PlatformDirectedOffline </b>to bring an <a href="https://msdn.microsoft.com/0dd010e7-3e10-422a-adcb-8fe7df9e29ab">ECC</a> memory page into an offline state.

For more information about PFA support for WHEA, see <a href="https://msdn.microsoft.com/d2ded330-edcc-4bdd-9b52-73c1961d8ef2">Predictive Failure Analysis (PFA)</a>.


<div class="alert"><b>Note</b>  This member is supported in Windows 7 and later versions of Windows.</div>
<div> </div>



#### - PreviousError

A single bit that indicates whether the hardware error packet contains information about a fatal hardware error. This error caused the operating system to generate a bug check and restart.


#### - Reserved1

Reserved for system use.


<div class="alert"><b>Note</b>  In versions of the Windows Driver Kit (WDK) prior to Windows 7, this member was named <b>CpuValid</b>. The <b>CpuValid </b>member has been deprecated in the WDK for Windows 7 and later versions of Windows.</div>
<div> </div>



#### - Reserved2

Reserved for system use. 


#### - Simulated

A single bit that indicates that the error condition was simulated.


## -remarks



The WHEA_ERROR_PACKET_FLAGS union describes the error condition reported by using a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560465">WHEA_ERROR_PACKET</a> structure.




## -see-also

<a href="https://msdn.microsoft.com/d2ded330-edcc-4bdd-9b52-73c1961d8ef2">Predictive Failure Analysis (PFA)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560465">WHEA_ERROR_PACKET</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_ERROR_PACKET_FLAGS union%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

