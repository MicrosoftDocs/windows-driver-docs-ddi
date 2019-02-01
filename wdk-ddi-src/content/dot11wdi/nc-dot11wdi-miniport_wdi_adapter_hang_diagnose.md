---
UID: NC:dot11wdi.MINIPORT_WDI_ADAPTER_HANG_DIAGNOSE
title: MINIPORT_WDI_ADAPTER_HANG_DIAGNOSE (dot11wdi.h)
description: The MiniportWdiAdapterHangDiagnose handler function is used to collect hardware control register states and optionally full firmware state.
old-location: netvista\miniportwdiadapterhangdiagnose.htm
tech.root: netvista
ms.assetid: 233CCF43-481E-4759-A2FC-0329103F8208
ms.date: 05/02/2018
ms.keywords: MINIPORT_WDI_ADAPTER_HANG_DIAGNOSE, MINIPORT_WDI_ADAPTER_HANG_DIAGNOSE callback, MiniportWdiAdapterHangDiagnose, MiniportWdiAdapterHangDiagnose callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiAdapterHangDiagnose, netvista.miniportwdiadapterhangdiagnose
ms.topic: callback
req.header: dot11wdi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	UserDefined
api_location:
-	dot11wdi.h
api_name:
-	MiniportWdiAdapterHangDiagnose
product:
- Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_WDI_ADAPTER_HANG_DIAGNOSE callback function


## -description


The MiniportWdiAdapterHangDiagnose handler function is used to collect hardware control register states and optionally full firmware state.

This is a WDI miniport handler inside <a href="https://msdn.microsoft.com/library/windows/hardware/mt297617">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_ADAPTER_HANG_DIAGNOSE</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportDriverContext [in]

The handle to a driver-allocated context area where the driver maintains state and configuration information. The miniport driver passed this context area to the <a href="https://msdn.microsoft.com/library/windows/hardware/mt297596">NdisMRegisterWdiMiniportDriver</a> function.


### -param DiagnoseLevel [in]

The diagnose level, as defined in the <a href="https://msdn.microsoft.com/library/windows/hardware/mt297626">eDiagnoseLevel</a> enumeration. The default level is <b>DiagnoseLevelHardwareRegisters</b>, 1KB maximum in the output buffer.


### -param BufferSize [in]

The size of <b>FirmwareBlob</b>, in bytes.


### -param *FirmwareBlob [out]

A pointer to the buffer that  will contain the hardware control registry states, and optionally full firmware state.


### -param *pOutputSize [out]

A pointer to the number of bytes written to <b>FirmwareBlob</b>.


## -returns



The return value is ignored.

<h3><a id="Remarks"></a><a id="remarks"></a><a id="REMARKS"></a>Remarks</h3>
    The default diagnose level is <b>DiagnoseLevelHardwareRegisters</b>, with 1KB maximum in the output buffer.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt297617">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/wdi-hang-detection-and-recovery">WDI hang detection and recovery</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297626">eDiagnoseLevel</a>
 

 

