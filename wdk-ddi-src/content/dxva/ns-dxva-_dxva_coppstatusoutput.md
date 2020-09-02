---
UID: NS:dxva._DXVA_COPPStatusOutput
title: _DXVA_COPPStatusOutput (dxva.h)
description: The DXVA_COPPStatusOutput structure describes the status returned from a query on a protected video session that is associated with a DirectX VA COPP device.
old-location: display\dxva_coppstatusoutput.htm
tech.root: display
ms.assetid: 71d16b59-3e5c-4a2a-9217-5e0f7a2d4478
ms.date: 05/10/2018
keywords: ["DXVA_COPPStatusOutput structure"]
ms.keywords: "*LPDXVA_COPPStatusOutput, DXVA_COPPStatusOutput, DXVA_COPPStatusOutput structure [Display Devices], LPDXVA_COPPStatusOutput, LPDXVA_COPPStatusOutput structure pointer [Display Devices], _DXVA_COPPStatusOutput, display.dxva_coppstatusoutput, dxva/DXVA_COPPStatusOutput, dxva/LPDXVA_COPPStatusOutput, dxvaref_4b7212ce-7beb-45c6-b5dd-92922993595f.xml"
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: This structure applies only to Windows Server 2003 with SP1 and later, and Windows XP with SP2 and later.
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
targetos: Windows
req.typenames: DXVA_COPPStatusOutput, *LPDXVA_COPPStatusOutput
f1_keywords:
 - _DXVA_COPPStatusOutput
 - dxva/_DXVA_COPPStatusOutput
 - LPDXVA_COPPStatusOutput
 - dxva/LPDXVA_COPPStatusOutput
 - DXVA_COPPStatusOutput
 - dxva/DXVA_COPPStatusOutput
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dxva.h
api_name:
 - DXVA_COPPStatusOutput
---

# _DXVA_COPPStatusOutput structure


## -description

The DXVA_COPPStatusOutput structure describes the status returned from a query on a protected video session that is associated with a DirectX VA COPP device.

## -struct-fields

### -field macKDI

Specifies a message authentication code (MAC) GUID for the status at <b>COPPStatus</b>. The application that requested the status can use the MAC to verify that the transmission of the status was secure (that is, it was not tampered with in transit from the driver).

### -field cbSizeData

Specifies the size, in bytes, of the status data at <b>COPPStatus</b>.

### -field COPPStatus

Specifies an array that contains the status data. The display driver should return status data in one of the following ways, depending on the input value that was specified in the <b>guidStatusRequestID</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_coppstatusinput">DXVA_COPPStatusInput</a> structure: 

| ****Input value**** | ****Output status data**** | 
|:--|:--|
| DXVA_COPPQueryDisplayData | Pointer to a [DXVA_COPPStatusDisplayData](https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_coppstatusdisplaydata)  structure | 
| DXVA_COPPQueryProtectionType, DXVA_COPPQueryConnectorType, DXVA_COPPQueryLocalProtectionLevel, DXVA_COPPQueryGlobalProtectionLevel or DXVA_COPPQueryBusData| Pointer to a [DXVA_COPPStatusData](https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_coppstatusdata)  structure | 
| DXVA_COPPQueryHDCPKeyData | Pointer to a [DXVA_COPPStatusHDCPKeyData](https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_coppstatushdcpkeydata)  structure | 
| DXVA_COPPQuerySignaling | Pointer to a [DXVA_COPPStatusSignalingCmdData](https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_coppstatussignalingcmddata)  structure |

## -remarks

Status requests are passed in the <i>pInput</i> parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/display/coppquerystatus">COPPQueryStatus</a> function. The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_coppstatusinput">DXVA_COPPStatusInput</a> structure describes a request for status. Status information is returned through the <i>pOutput</i> parameter of <i>COPPQueryStatus</i>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/display/coppquerystatus">COPPQueryStatus</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_coppsetprotectionlevelcmddata">DXVA_COPPSetProtectionLevelCmdData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_coppstatusdata">DXVA_COPPStatusData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_coppstatusdisplaydata">DXVA_COPPStatusDisplayData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_coppstatushdcpkeydata">DXVA_COPPStatusHDCPKeyData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_coppstatusinput">DXVA_COPPStatusInput</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_coppstatussignalingcmddata">DXVA_COPPStatusSignalingCmdData</a>

