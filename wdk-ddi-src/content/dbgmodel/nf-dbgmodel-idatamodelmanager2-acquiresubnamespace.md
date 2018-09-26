---
UID: NF:dbgmodel.IDataModelManager2.AcquireSubNamespace
title: IDataModelManager2::AcquireSubNamespace
author: windows-driver-content
description: TBD
ms.assetid: 2cb6ec25-f9aa-419f-80f5-845a327ea7c2
ms.author: windowsdriverdev
ms.date: 08/21/2018
ms.topic: method
ms.keywords: IDataModelManager2::AcquireSubNamespace, AcquireSubNamespace, IDataModelManager2.AcquireSubNamespace, IDataModelManager2::AcquireSubNamespace, IDataModelManager2.AcquireSubNamespace
req.header: dbgmodel.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
-	apiref
api_type: 
-	COM
api_location: 
-	dbgmodel.h
api_name: 
-	IDataModelManager2.AcquireSubNamespace
product: Windows
targetos: Windows


tech.root: debugger
---

# IDataModelManager2::AcquireSubNamespace


## -description

The AcquireSubNamespace method helps in the construction of something which might more traditionally look like a language namespace than a new object in a dynamic language. If, for instance, a caller wishes to categorize properties on a process object to make the process object more organized and the properties easier to discover, one method of doing this would be to create a sub-object for each category on the process object and placing those properties inside that object. The problem with this notion is that the sub-object has its own context and the properties there are passed the sub-object as an instance pointer instead of the process object itself. The AcquireSubNamespace method helps to create a shared ownership "sub-object" where the instance pointer passed to properties of the sub-object is the parent object. 

As an example, consider a process object to which we want to add a Heaps property representing the process heap (and all other custom heaps within the process). It might initially appear as follows: 

    • Process [foo.exe] 
        o Heaps [3 heaps]

Since the process object may have many other fields and there may be many things associated with Memory in the process, a better paradigm might be: 

    • Process [foo.exe] 
        o Memory [A namespace of things associated with Memory in the process] 
             Heaps   

If the Memory object above is simply a normal property which returns a new object, when a caller asks for someProcess.Memory.Heaps, the property accessor for the Heaps property will be passed a context object (this pointer) of the newly created Memory object with no easy way to get back to other attributes of the process. If the Memory object is instead created with the AcquireSubNamespace method, the paradigm looks as above excepting that the property accessor for anything on the Memory object will instead be the process object itself. This allows the Heaps property implementation to easily get back to other attributes of the process. This style of object is a sub-namespace instead of a sub-object. 

It is important to note that there is nothing which the AcquireSubNamespace method does which cannot be accomplished with other methods. In effect, this is a helper method which does the following: 

    • Checks if there is a model registered under the name given by subNamespaceModelName. If so, returns it. If not, proceeds to: 

      o Creates and registers a new model under the name given by subNamespaceModelName
      o Acquires the model registered under the name given by modelName.
      o Adds a new property named according to accessName with metadata supplied by the metadata argument. The accessor for this property returns a new object with special properties: 
         The new object has the model created and registered under subNamespaceModelName attached as a parent.
         The parent model has a context adjustor. The context adjustor is a property.
         The context adjustor property getter returns the original process object.

Once a sub-namespace is created, its ownership is considered shared amongst all potential callers of the AcquireSubNamespace method with the same set of arguments. As a shared ownership semantic, it is improper to unregister a sub-namespace arbitrarily. 


## -parameters

### -param modelName
The name of the data model which is being extended with a sub-namespace.

### -param subNamespaceModelName
The name of the data model which represents the sub-namespace itself. The newly created sub-namespace is a data model which will be registered under this name.

### -param accessName
A property of this name will be added to the data model registered under the name given by the modelName argument in order to access the sub-namespace.

### -param metadata
Optional metadata to be associated with the key given by accessName in the event that this call is the one which creates the shared sub-namespace.

### -param namespaceModelObject
The data model representing the sub-namespace will be returned here. This data model may have been created by a prior call to the AcquireSubNamespace method or by the current call. The ownership is considered shared amongst all callers.


## -returns
This method returns HRESULT.

## -remarks

**Sample Code**

```cpp
ComPtr<IDataModelManager> spManager;   /* get the data model manager */
ComPtr<IModelObject> spExtensionModel; /* get a data model you want to extend 
                                          some namespace with (see
                                          CreateDataModelObject) */

// Add a shared namespace called "Memory" to Process.  Then extend this namespace 
// with spExtensionModel
ComPtr<IModelObject> spProcessMemory;
if (SUCCEEDED(spManager->AcquireSubNamespace(
    L"Debugger.Models.Process", 
    L"Debugger.Models.Process.Memory", 
    L"Memory", 
    nullptr /* probably should have help metadata! */, 
    &spProcessMemory)))
{
    if (SUCCEEDED(spProcessMemory->AddParentModel(spExtensionModel.Get(), 
                                                  nullptr, 
                                                  false)))
    {
        // The properties on spExtensionModel are now in "Process.Memory.*"
        // In addition, the context (*this*) pointer passed to properties on
        // spExtensionModel is the process object itself, not some empty 
        // synthetic created for the namespace!
    }
}
```

## -see-also

[IDataModelManager2 interface](nn-dbgmodel-idatamodelmanager2.md)
