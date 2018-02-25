---
UID: NS:portcls._PCPROPERTY_REQUEST
title: "_PCPROPERTY_REQUEST"
author: windows-driver-content
description: The PCPROPERTY_REQUEST structure specifies a property request.
old-location: audio\pcproperty_request.htm
old-project: audio
ms.assetid: 3683735d-ce00-4615-9782-dee9f4753cc7
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , *, *PPCPROPERTY_REQUEST, ,, C, E, O, P, PCPROPERTY_REQUEST, PCPROPERTY_REQUEST structure [Audio Devices], PPCPROPERTY_REQUEST, PPCPROPERTY_REQUEST structure pointer [Audio Devices], Q, R, S, T, U, Y, _, _PCPROPERTY_REQUEST, audio.pcproperty_request, audpc-struct_f153c6fb-8b21-4a81-ab9b-d7b7fef9f9db.xml, portcls/PCPROPERTY_REQUEST, portcls/PPCPROPERTY_REQUEST"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: portcls.h
req.include-header: Portcls.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	portcls.h
apiname:
-	PCPROPERTY_REQUEST
product: Windows
targetos: Windows
req.typenames: PCPROPERTY_REQUEST, *PPCPROPERTY_REQUEST, PCPROPERTY_REQUEST, *PPCPROPERTY_REQUEST
---

# _PCPROPERTY_REQUEST structure


## -description


The <b>PCPROPERTY_REQUEST</b> structure specifies a property request.


## -syntax


````
typedef struct _PCPROPERTY_REQUEST {
  PUNKNOWN              MajorTarget;
  PUNKNOWN              MinorTarget;
  ULONG                 Node;
  const PCPROPERTY_ITEM *PropertyItem;
  ULONG                 Verb;
  ULONG                 InstanceSize;
  PVOID                 Instance;
  ULONG                 ValueSize;
  PVOID                 Value;
  PIRP                  Irp;
} PCPROPERTY_REQUEST, *PPCPROPERTY_REQUEST;
````


## -struct-fields




### -field MajorTarget


<a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> pointer to the main miniport object. This member contains the <i>UnknownMiniport</i> parameter value that the adapter driver previously passed to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536943">IPort::Init</a> method.


### -field MinorTarget


<a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> pointer to a stream object that is associated with the <b>MajorTarget</b> miniport object. If the target for the property request is a pin instance, this member contains the stream-object pointer that the IMiniport <i>Xxx</i>::NewStream method previously output to the port driver (for example, the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536723">IMiniportWaveCyclic::NewStream</a> method's <i>Stream</i> parameter). Otherwise (if the target for the property request is a filter instance), this member is <b>NULL</b>.


### -field Node

Specifies a node ID. This member identifies the target node for the request. If the target is not a node, this member is set to ULONG(-1).


### -field PropertyItem

Pointer to the property item, which is a structure of type <a href="..\portcls\ns-portcls-__unnamed_struct_0cb6_3.md">PCPROPERTY_ITEM</a>.


### -field Verb

Specifies the type of property request. <b>Verb</b> is set to the bitwise OR of one or more of the following flag bits from header file ks.h:

<ul>
<li>
KSPROPERTY_TYPE_GET

</li>
<li>
KSPROPERTY_TYPE_SET

</li>
<li>
KSPROPERTY_TYPE_SETSUPPORT

</li>
<li>
KSPROPERTY_TYPE_BASICSUPPORT

</li>
<li>
KSPROPERTY_TYPE_RELATIONS

</li>
<li>
KSPROPERTY_TYPE_SERIALIZESET

</li>
<li>
KSPROPERTY_TYPE_UNSERIALIZESET

</li>
<li>
KSPROPERTY_TYPE_SERIALIZERAW

</li>
<li>
KSPROPERTY_TYPE_UNSERIALIZERAW

</li>
<li>
KSPROPERTY_TYPE_SERIALIZESIZE

</li>
<li>
KSPROPERTY_TYPE_DEFAULTVALUES

</li>
<li>
KSPROPERTY_TYPE_TOPOLOGY

</li>
</ul>
These flags are described in <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>.


### -field InstanceSize

Specifies the size in bytes of the property-instance buffer.


### -field Instance

Pointer to the property-instance buffer


### -field ValueSize

Specifies the size in bytes of the property-value buffer.


### -field Value

Pointer to the property-value buffer


### -field Irp

Pointer to the <a href="..\wdm\ns-wdm-_irp.md">IRP</a> containing the client's original property request


## -remarks



This is the structure that the port driver passes to the miniport driver's property-handler routine. The <a href="..\portcls\ns-portcls-__unnamed_struct_0cb6_3.md">PCPROPERTY_ITEM</a> structure contains a function pointer to a property handler that takes a <b>PCPROPERTY_REQUEST</b> pointer as its only call parameter. The port driver allocates a <b>PCPROPERTY_REQUEST</b> structure, extracts the relevant information from the original property request (which the <b>Irp</b> member points to), and loads the information into this structure before calling the handler.

In WDM audio, the target of a property request can be either a filter instance or a pin instance. The target can also include a node ID.

In the client's original property request, the property-instance data always begins with a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a> or <a href="..\ksmedia\ns-ksmedia-ksnodeproperty.md">KSNODEPROPERTY</a> structure, but can include additional information. The port driver adjusts the <b>PCPROPERTY_REQUEST</b> structure's <b>Instance</b> member to point to this additional information, if it exists. For details, see <a href="https://msdn.microsoft.com/4bf176ae-b3fd-47e6-9802-a92ef5e9904f">Audio Property Handlers</a>.

The <b>MajorTarget</b> and <b>MinorTarget</b> members are <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> pointers to the main miniport object and an associated stream object, respectively. The property handler can query these objects for their miniport and stream interfaces. If the target for the property request is a filter instance, <b>MajorTarget</b> points to the miniport object for that filter instance, and <b>MinorTarget</b> is <b>NULL</b>. If the target is a pin instance, <b>MinorTarget</b> points to the stream object for that pin, and <b>MajorTarget</b> points to the miniport object for the filter that the pin is attached to.

For example, if the target for the property request is a pin instance on a WaveCyclic filter:

<ul>
<li>
The handler can call <a href="https://msdn.microsoft.com/54d5ff80-18db-43f2-b636-f93ac053146d">QueryInterface</a> on the <b>MajorTarget</b> object's <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface to obtain a reference to the object's <a href="..\portcls\nn-portcls-iminiportwavecyclic.md">IMiniportWaveCyclic</a> interface.

</li>
<li>
The handler can call <a href="https://msdn.microsoft.com/54d5ff80-18db-43f2-b636-f93ac053146d">QueryInterface</a> on the <b>MinorTarget</b> object's <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface to obtain a reference to the object's <a href="..\portcls\nn-portcls-iminiportwavecyclicstream.md">IMiniportWaveCyclicStream</a> interface.

</li>
</ul>
For background information about audio properties, see <a href="https://msdn.microsoft.com/ffc5834f-30c8-40b5-b57b-fe784331690c">Audio Endpoints, Properties and Events</a>. For a list of the available audio-specific properties, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff536197">Audio Drivers Property Sets</a>.




## -see-also

<a href="..\ksmedia\ns-ksmedia-ksnodeproperty_audio_channel.md">KSNODEPROPERTY_AUDIO_CHANNEL</a>



<a href="..\ksmedia\ns-ksmedia-ksnodeproperty.md">KSNODEPROPERTY</a>



<a href="..\portcls\ns-portcls-__unnamed_struct_0cb6_3.md">PCPROPERTY_ITEM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PCPROPERTY_REQUEST structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

