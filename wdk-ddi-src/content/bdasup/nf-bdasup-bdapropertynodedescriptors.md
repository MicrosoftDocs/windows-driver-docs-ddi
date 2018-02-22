---
UID: NF:bdasup.BdaPropertyNodeDescriptors
title: BdaPropertyNodeDescriptors function
author: windows-driver-content
description: The BdaPropertyNodeDescriptors function retrieves a list of nodes in a template topology.
old-location: stream\bdapropertynodedescriptors.htm
old-project: stream
ms.assetid: 46e38460-9284-4305-997d-bf72b308f301
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: BdaPropertyNodeDescriptors, bdasup/BdaPropertyNodeDescriptors, stream.bdapropertynodedescriptors, bdaref_67976a51-5f21-4369-be96-ab6a2b758e85.xml, BdaPropertyNodeDescriptors function [Streaming Media Devices]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Bdasup.lib
-	Bdasup.dll
apiname:
-	BdaPropertyNodeDescriptors
product: Windows
targetos: Windows
req.typenames: "*PKSP_BDA_NODE_PIN, KSP_BDA_NODE_PIN"
---

# BdaPropertyNodeDescriptors function


## -description


The <b>BdaPropertyNodeDescriptors</b> function retrieves a list of nodes in a template topology. 


## -syntax


````
NTSTATUS BdaPropertyNodeDescriptors(
  _In_      PIRP               Irp,
  _In_      PKSPROPERTY        pKSProperty,
  _Out_opt_ BDANODE_DESCRIPTOR *pguidProperty
);
````


## -parameters




### -param pIrp

TBD


### -param pKSProperty [in]

Points to a <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a> structure that describes the property and request type of the property request.


### -param pNodeDescriptorProperty

TBD




#### - Irp [in]

Points to the IRP for the request to retrieve the list of nodes. The BDA minidriver receives this IRP with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564324">KSPROPERTY_BDA_NODE_DESCRIPTORS</a> request.


#### - pguidProperty [out, optional]

Points to an array that receives the list of GUIDs for the nodes in a template topology. 


## -returns



Returns STATUS_SUCCESS or an appropriate error code. 




## -remarks



A BDA minidriver calls the <b>BdaPropertyNodeDescriptors</b> function to retrieve the list of nodes after the minidriver receives a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564324">KSPROPERTY_BDA_NODE_DESCRIPTORS</a> request of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566561">KSPROPSETID_BdaTopology</a> property set from the network provider. Most BDA minidrivers can define dispatch and filter-automation tables so that those minidrivers dispatch the <b>BdaPropertyNodeDescriptors</b> function directly, without intercepting this request using an internal get-handler (<a href="https://msdn.microsoft.com/library/windows/hardware/ff567177">KStrGetPropertyHandler</a>). See <a href="https://msdn.microsoft.com/1c0dace6-b618-4705-bf5d-65457d14c072">Defining Automation Tables</a> and <a href="https://msdn.microsoft.com/fdac317e-d4fc-47c9-87d3-bec597f758f5">Determining BDA Device Topology</a> for more information. 

For a list of BDA nodes that are available to create in a template topology, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff556529">BDA Node Category GUIDs</a>. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566561">KSPROPSETID_BdaTopology</a>



<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566561">KSPROPSETID_BdaTopology</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20BdaPropertyNodeDescriptors function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

