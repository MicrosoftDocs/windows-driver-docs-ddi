---
UID: NF:bdasup.BdaPropertyNodeMethods
title: BdaPropertyNodeMethods function
author: windows-driver-content
description: The BdaPropertyNodeMethods function retrieves a list of methods that a node supports.
old-location: stream\bdapropertynodemethods.htm
old-project: stream
ms.assetid: 52cb13a6-6efe-4934-a6ec-178d4b2afb0a
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: BdaPropertyNodeMethods, BdaPropertyNodeMethods function [Streaming Media Devices], bdaref_15a0d157-4e7d-43ae-9f1f-6ffb70bd4f9b.xml, bdasup/BdaPropertyNodeMethods, stream.bdapropertynodemethods
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: bdasup.h
req.include-header: Bdasup.h
req.target-type: Desktop
req.target-min-winverclnt: Available on Microsoft Windows XP and later operating systems. This routine is available on the Windows 2000 platform only if Microsoft DirectX 9.0 and later is installed on that platform.
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
req.lib: Bdasup.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Bdasup.lib
-	Bdasup.dll
api_name:
-	BdaPropertyNodeMethods
product: Windows
targetos: Windows
req.typenames: KSP_BDA_NODE_PIN, *PKSP_BDA_NODE_PIN
---

# BdaPropertyNodeMethods function


## -description


The <b>BdaPropertyNodeMethods</b> function retrieves a list of methods that a node supports. 


## -syntax


````
NTSTATUS BdaPropertyNodeMethods(
  _In_      PIRP      Irp,
  _In_      PKSP_NODE pKSProperty,
  _Out_opt_ GUID      *pguidProperty
);
````


## -parameters




### -param pIrp

TBD


### -param pKSProperty [in]

Points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a> structure that describes the property and request type of the property request.


### -param pguidProperty [out, optional]

Points to an array that receives the list of GUIDs for the methods supported by a node.


#### - Irp [in]

Points to the IRP for the request to retrieve the list of methods for a node. The BDA minidriver receives this IRP with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564328">KSPROPERTY_BDA_NODE_METHODS</a> request.


## -returns



Returns STATUS_SUCCESS or an appropriate error code. 




## -remarks



A BDA minidriver calls the <b>BdaPropertyNodeMethods</b> function to retrieve the list of methods for a node after the minidriver receives a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564328">KSPROPERTY_BDA_NODE_METHODS</a> request of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566561">KSPROPSETID_BdaTopology</a> property set from the network provider. Most BDA minidrivers can define dispatch and filter-automation tables so that those minidrivers dispatch the <b>BdaPropertyNodeMethods</b> function directly, without intercepting this request using an internal get-handler (<a href="https://msdn.microsoft.com/library/windows/hardware/ff567177">KStrGetPropertyHandler</a>). See <a href="https://msdn.microsoft.com/1c0dace6-b618-4705-bf5d-65457d14c072">Defining Automation Tables</a> and <a href="https://msdn.microsoft.com/fdac317e-d4fc-47c9-87d3-bec597f758f5">Determining BDA Device Topology</a> for more information. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566561">KSPROPSETID_BdaTopology</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564328">KSPROPERTY_BDA_NODE_METHODS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20BdaPropertyNodeMethods function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

