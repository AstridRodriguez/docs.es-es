---
title: 'Cómo: Proporcionar un mapa de bits del cuadro de herramientas para un control'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Toolbox [Windows Forms], adding bitmaps for custom controls
- custom controls [Windows Forms], Toolbox bitmaps
- bitmaps [Windows Forms], custom controls
ms.assetid: 0ed0840a-616d-41ba-a27d-3573241932ad
ms.openlocfilehash: aa32850b9bcd1a15a93bd6c80b2278278d12c417
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43746550"
---
# <a name="how-to-provide-a-toolbox-bitmap-for-a-control"></a>Cómo: Proporcionar un mapa de bits del cuadro de herramientas para un control
Si desea tener un icono especial para el control aparezca en el **cuadro de herramientas**, puede especificar una imagen determinada mediante el <xref:System.Drawing.ToolboxBitmapAttribute>. Esta clase es un *atributo*, un tipo especial de clase que se puede asociar a otras clases. Para obtener más información acerca de los atributos, vea [información general de atributos (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/index.md) para Visual Basic o [atributos (C#)](../../../csharp/programming-guide/concepts/attributes/index.md) para C#.  
  
 Mediante el <xref:System.Drawing.ToolboxBitmapAttribute>, puede especificar una cadena que indica la ruta de acceso y nombre de archivo para un mapa de bits de 16 por 16 píxeles. Este mapa de bits aparecerá junto al control cuando se agregue al **cuadro de herramientas**. También puede especificar un <xref:System.Type>, en cuyo caso se carga el mapa de bits asociado con ese tipo. Si especifica tanto un <xref:System.Type> y una cadena, el control busca un recurso de imagen con el nombre especificado por el parámetro de cadena en el ensamblado que contiene el tipo especificado por el <xref:System.Type> parámetro.  
  
### <a name="to-specify-a-toolbox-bitmap-for-your-control"></a>Para especificar un mapa de bits del cuadro de herramientas para el control  
  
1.  Agregar el <xref:System.Drawing.ToolboxBitmapAttribute> a la declaración de clase del control antes de la `Class` palabra clave de visual Basic y sobre la declaración de clase de Visual C#.  
  
    ```vb  
    ' Specifies the bitmap associated with the Button type.  
    <ToolboxBitmap(GetType(Button))> Class MyControl1  
    ' Specifies a bitmap file.  
    End Class  
    <ToolboxBitmap("C:\Documents and Settings\Joe\MyPics\myImage.bmp")> _  
       Class MyControl2  
    End Class  
    ' Specifies a type that indicates the assembly to search, and the name   
    ' of an image resource to look for.  
    <ToolboxBitmap(GetType(MyControl), "MyControlBitmap")> Class MyControl  
    End Class  
    ```  
  
    ```csharp  
    // Specifies the bitmap associated with the Button type.  
    [ToolboxBitmap(typeof(Button))]  
    class MyControl1 : UserControl  
    {  
    }  
    // Specifies a bitmap file.  
    [ToolboxBitmap(@"C:\Documents and Settings\Joe\MyPics\myImage.bmp")]  
    class MyControl2 : UserControl  
    {  
    }  
    // Specifies a type that indicates the assembly to search, and the name   
    // of an image resource to look for.  
    [ToolboxBitmap(typeof(MyControl), "MyControlBitmap")]  
    class MyControl : UserControl  
    {  
    }  
    ```  
  
2.  Recompile el proyecto.  
  
    > [!NOTE]
    >  El mapa de bits no aparece en el cuadro de herramientas para componentes y controles generados automáticamente. Para ver el mapa de bits, vuelva a cargar el control con el cuadro de diálogo **Elegir elementos del cuadro de herramientas**. Para más información, consulte [Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Drawing.ToolboxBitmapAttribute>
- [Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
- [Desarrollar controles de Windows Forms en tiempo de diseño](developing-windows-forms-controls-at-design-time.md)
- [Información general sobre los atributos (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [Atributos (C#)](../../../csharp/programming-guide/concepts/attributes/index.md)
