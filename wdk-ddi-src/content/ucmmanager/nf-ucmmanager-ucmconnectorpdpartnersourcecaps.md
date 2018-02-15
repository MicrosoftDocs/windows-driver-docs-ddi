---
UID: NF:ucmmanager.UcmConnectorPdPartnerSourceCaps
title: UcmConnectorPdPartnerSourceCaps function
author: windows-driver-content
description: Notifies the USB connector manager framework extension (UcmCx) with the power source capabilities of the partner connector.
old-location: buses\ucmconnectorpdportpartnersourcecaps.htm
old-project: usbref
ms.assetid: 282E12E2-F16F-4399-BC8C-78BD64F05F13
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: UcmConnectorPdPartnerSourceCaps method [Buses], UcmConnectorPdPartnerSourceCaps, ucmmanager/UcmConnectorPdPartnerSourceCaps, buses.ucmconnectorpdportpartnersourcecaps
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	UcmCxstub.lib
-	UcmCxstub.dll
apiname:
-	UcmConnectorPdPartnerSourceCaps
product: Windows
targetos: Windows
req.typenames: PORT_DATA_1, *PPORT_DATA_1
req.product: Windows 10 or later.
---

# UcmConnectorPdPartnerSourceCaps function


## -description


Notifies the USB connector manager framework extension (UcmCx) with the power source capabilities of the partner connector.


## -syntax


````
NTSTATUS UcmConnectorPdPartnerSourceCaps(
  [in] UCMCONNECTOR              Connector,
  [in] UCM_PD_POWER_DATA_OBJECT  Pdos[],
  [in] UCHAR                     PdoCount
);
````


## -parameters




### -param Connector [in]

Handle to the connector object that the client driver received in the previous call to <a href="..\ucmmanager\nf-ucmmanager-ucmconnectorcreate.md">UcmConnectorCreate</a>.


### -param Pdos

TBD


### -param PdoCount [in]

Number of elements in the array specified by   <i>Pdos[]</i>.


#### - Pdos[] [in]

A caller-allocated array of <a href="..\ucmtypes\ns-ucmtypes-_ucm_pd_power_data_object.md">UCM_PD_POWER_DATA_OBJECT</a> structures that describes the power source capabilities.


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

<a href="..\ucmmanager\nf-ucmmanager-ucmconnectorcreate.md">UcmConnectorCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UcmConnectorPdPartnerSourceCaps method%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

