---
UID: NF:ucmmanager.UcmConnectorPdPartnerSourceCaps
title: UcmConnectorPdPartnerSourceCaps function
description: Notifies the USB connector manager framework extension (UcmCx) with the power source capabilities of the partner connector.
old-location: buses\ucmconnectorpdportpartnersourcecaps.htm
tech.root: usbref
ms.assetid: 282E12E2-F16F-4399-BC8C-78BD64F05F13
ms.date: 05/07/2018
ms.keywords: UcmConnectorPdPartnerSourceCaps, UcmConnectorPdPartnerSourceCaps method [Buses], buses.ucmconnectorpdportpartnersourcecaps, ucmmanager/UcmConnectorPdPartnerSourceCaps
ms.topic: function
req.header: ucmmanager.h
req.include-header: Ucmcx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 2.15
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: UcmCxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	UcmCxstub.lib
-	UcmCxstub.dll
api_name:
-	UcmConnectorPdPartnerSourceCaps
product:
- Windows
targetos: Windows
req.typenames: 
---

# UcmConnectorPdPartnerSourceCaps function


## -description


Notifies the USB connector manager framework extension (UcmCx) with the power source capabilities of the partner connector.


## -parameters




### -param Connector [in]

Handle to the connector object that the client driver received in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt187909">UcmConnectorCreate</a>.


### -param Pdos

<p>A caller-allocated array of <a href="https://msdn.microsoft.com/library/Mt187935(v=VS.85).aspx"><b>UCM_PD_POWER_DATA_OBJECT</b></a> structures that describes the power source capabilities.</p>


### -param PdoCount [in]

Number of elements in the array specified by   <i>Pdos[]</i>.


## -returns



<b>UcmConnectorPdPartnerSourceCaps</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> value. 




## -remarks



When using a Type-C connector for charging by using the power delivery (PD) mechanism, the local connector queries the partner connector for its supported power sourcing capabilities. That query is not required if the partner connector is the power source because in that case, the local connector cached the initial advertisement when the partner connector was attached. 	If the source capabilities changed, it sends an update to the local connector. 

If the partner connector is the power sink, the local connector port must query for the latest capabilities.



#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>        UCM_PD_POWER_DATA_OBJECT Pdos[1];

        UCM_PD_POWER_DATA_OBJECT_INIT_FIXED(&amp;Pdos[0]);

        Pdos[0].FixedSupplyPdo.VoltageIn50mV = 100;         // 5V
        Pdos[0].FixedSupplyPdo.MaximumCurrentIn10mA = 150;  // 1.5 A

        status = UcmConnectorPdPartnerSourceCaps(
            Connector,
            Pdos,
            ARRAYSIZE(Pdos));
        if (!NT_SUCCESS(status))
        {
            TRACE_ERROR(
                "UcmConnectorPdPartnerSourceCaps() failed with %!STATUS!.",
                status);
            goto Exit;
        }
</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt187909">UcmConnectorCreate</a>
 

 

