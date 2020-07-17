---
UID: NS:ntddk._WHEA_ERROR_PACKET_FLAGS
title: _WHEA_ERROR_PACKET_FLAGS (ntddk.h)
description: The WHEA_ERROR_PACKET_FLAGS union defines the error condition reported through a WHEA_ERROR_PACKET structure.
old-location: whea\whea_error_packet_flags.htm
tech.root: whea
ms.assetid: e1dae7df-7d81-42cc-9a01-44345f53ba4e
ms.date: 02/20/2018
keywords: ["_WHEA_ERROR_PACKET_FLAGS structure"]
ms.keywords: "*PWHEA_ERROR_PACKET_FLAGS, PWHEA_ERROR_PACKET_FLAGS, PWHEA_ERROR_PACKET_FLAGS union pointer [WHEA Drivers and Applications], WHEA_ERROR_PACKET_FLAGS, WHEA_ERROR_PACKET_FLAGS union [WHEA Drivers and Applications], _WHEA_ERROR_PACKET_FLAGS, ntddk/PWHEA_ERROR_PACKET_FLAGS, ntddk/WHEA_ERROR_PACKET_FLAGS, whea.whea_error_packet_flags, whearef_c193e4e7-f233-4de0-93ac-5e7b841a6c6e.xml"
f1_keywords:
 - "ntddk/WHEA_ERROR_PACKET_FLAGS"
 - "WHEA_ERROR_PACKET_FLAGS"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddk.h
api_name:
- WHEA_ERROR_PACKET_FLAGS
product:
- Windows
targetos: Windows
req.typenames: WHEA_ERROR_PACKET_FLAGS, *PWHEA_ERROR_PACKET_FLAGS
---

# _WHEA_ERROR_PACKET_FLAGS structure


## -description


The WHEA_ERROR_PACKET_FLAGS union defines the error condition reported through a <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff560465(v=vs.85)">WHEA_ERROR_PACKET</a> structure.


## -struct-fields




### -field DUMMYSTRUCTNAME

 


### -field DUMMYSTRUCTNAME.PreviousError

A single bit that indicates whether the hardware error packet contains information about a fatal hardware error. This error caused the operating system to generate a bug check and restart.


### -field DUMMYSTRUCTNAME.Reserved1

Reserved for system use.


<div class="alert"><b>Note</b>  In versions of the Windows Driver Kit (WDK) prior to Windows 7, this member was named <b>CpuValid</b>. The <b>CpuValid </b>member has been deprecated in the WDK for Windows 7 and later versions of Windows.</div>
<div> </div>



### -field DUMMYSTRUCTNAME.HypervisorError

A single bit that indicates that a hypervisor error has occurred.


### -field DUMMYSTRUCTNAME.Simulated

A single bit that indicates that the error condition was simulated.


### -field DUMMYSTRUCTNAME.PlatformPfaControl

A single bit that indicates whether WHEA or a PSHED plug-in is in control of predictive failure analysis (PFA). If this bit is set, the PSHED plug-in is in control of PFA and must set the <b>PlatformDirectedOffline </b>to bring an <a href="https://docs.microsoft.com/windows-hardware/drivers/">ECC</a> memory page into an offline state.

For more information about PFA support for WHEA, see <a href="https://docs.microsoft.com/windows-hardware/drivers/whea/predictive-failure-analysis--pfa-">Predictive Failure Analysis (PFA)</a>.


<div class="alert"><b>Note</b>  This member is supported in Windows 7 and later versions of Windows.</div>
<div> </div>



### -field DUMMYSTRUCTNAME.PlatformDirectedOffline

A single bit that indicates whether the PSHED plug-in that performs PFA on a system component has determined if the component should be brought into an offline state. This bit is only valid if the <b>PlatformPfaControl</b> member is set.


<div class="alert"><b>Note</b>  This member is supported in Windows 7 and later versions of Windows.</div>
<div> </div>



### -field DUMMYSTRUCTNAME.Reserved2

Reserved for system use. 


### -field AsULONG

A ULONG representation of the contents of the WHEA_ERROR_PACKET_FLAGS union.


## -remarks



The WHEA_ERROR_PACKET_FLAGS union describes the error condition reported by using a <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff560465(v=vs.85)">WHEA_ERROR_PACKET</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/whea/predictive-failure-analysis--pfa-">Predictive Failure Analysis (PFA)</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff560465(v=vs.85)">WHEA_ERROR_PACKET</a>
 

 

