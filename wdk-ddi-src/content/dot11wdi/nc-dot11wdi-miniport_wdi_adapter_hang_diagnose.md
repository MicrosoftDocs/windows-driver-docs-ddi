---
UID: NC:dot11wdi.MINIPORT_WDI_ADAPTER_HANG_DIAGNOSE
title: MINIPORT_WDI_ADAPTER_HANG_DIAGNOSE
author: windows-driver-content
description: The MiniportWdiAdapterHangDiagnose handler function is used to collect hardware control register states and optionally full firmware state.
old-location: netvista\miniportwdiadapterhangdiagnose.htm
old-project: netvista
ms.assetid: 233CCF43-481E-4759-A2FC-0329103F8208
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.miniportwdiadapterhangdiagnose, MiniportWdiAdapterHangDiagnose callback function [Network Drivers Starting with Windows Vista], MiniportWdiAdapterHangDiagnose, MINIPORT_WDI_ADAPTER_HANG_DIAGNOSE, MINIPORT_WDI_ADAPTER_HANG_DIAGNOSE, dot11wdi/MiniportWdiAdapterHangDiagnose
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	dot11wdi.h
apiname:
-	MiniportWdiAdapterHangDiagnose
product: Windows
targetos: Windows
req.typenames: "*PSYNTH_STATS, SYNTH_STATS"
---

# MINIPORT_WDI_ADAPTER_HANG_DIAGNOSE callback


## -description


The MiniportWdiAdapterHangDiagnose handler function is used to collect hardware control register states and optionally full firmware state.

This is a WDI miniport handler inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics.md">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_ADAPTER_HANG_DIAGNOSE</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -prototype


````
MINIPORT_WDI_ADAPTER_HANG_DIAGNOSE MiniportWdiAdapterHangDiagnose;

NDIS_STATUS MiniportWdiAdapterHangDiagnose(
  _In_  NDIS_HANDLE    MiniportDriverContext,
  _In_  eDiagnoseLevel DiagnoseLevel,
  _In_  UINT32         BufferSize,
  _Out_ UINT8          *FirmwareBlob,
  _Out_ UINT32         *pOutputSize
)
{ ... }
````


## -parameters




### -param MiniportDriverContext [in]

The handle to a driver-allocated context area where the driver maintains state and configuration information. The miniport driver passed this context area to the <a href="..\dot11wdi\nf-dot11wdi-ndismregisterwdiminiportdriver.md">NdisMRegisterWdiMiniportDriver</a> function.


### -param DiagnoseLevel [in]

The diagnose level, as defined in the <a href="..\dot11wdi\ne-dot11wdi-ediagnoselevel.md">eDiagnoseLevel</a> enumeration. The default level is <b>DiagnoseLevelHardwareRegisters</b>, 1KB maximum in the output buffer.


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

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/wdi-hang-detection-and-recovery">WDI hang detection and recovery</a>



<a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics.md">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>



<a href="..\dot11wdi\ne-dot11wdi-ediagnoselevel.md">eDiagnoseLevel</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_WDI_ADAPTER_HANG_DIAGNOSE callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

