---
title: Добавление пользовательской проверки архитектуры в схемы зависимостей
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- dependency diagrams, adding custom validation
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: e9343ed8fdb1f3993fcd5c2f70595fd4bdd92dcd
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49875454"
---
# <a name="add-custom-architecture-validation-to-dependency-diagrams"></a>Добавление пользовательской проверки архитектуры в схемы зависимостей

В Visual Studio позволяет проверять исходный код в проекте по модели слоев и таким образом, убедитесь, что исходный код соответствие зависимостям на схеме зависимостей. В программе предусмотрен стандартный алгоритм проверки, однако вы можете определять собственные расширения проверки.

Когда пользователь выбирает **проверить архитектуру** команды на схеме зависимостей, вызывается стандартный метод проверки, после которого применяются все установленные расширения проверки.

> [!NOTE]
> На схеме зависимостей основная цель проверки является сравнение схемы с программным кодом в других частях решения.

Расширение проверки слоев можно упаковать в формат Visual Studio Integration Extension (VSIX) и предоставить его другим пользователям Visual Studio. Проверяющий элемент можно разместить в отдельном файле VSIX или объединить с другими расширениями. Код проверяющего элемента необходимо создавать в отдельном проекте Visual Studio, а не в проекте, содержащем другие расширения.

> [!WARNING]
> Создав проект проверки, скопируйте в него [пример кода](#example) , приведенный в конце этого раздела, и внесите в него изменения с учетом своих задач.

## <a name="requirements"></a>Требования

См. раздел [Требования](../modeling/extend-layer-diagrams.md#prereqs).

## <a name="defining-a-layer-validator-in-a-new-vsix"></a>Определение проверяющего элемента слоя в новом файле VSIX

Самый быстрый способ создать проверяющий элемент — это шаблон проекта. В этом случае код и манифест VSIX размещаются в одном и том же проекте.

### <a name="to-define-an-extension-by-using-a-project-template"></a>Определение расширения с использованием шаблона проекта

1. Создайте проект в новом решении, выбрав команду **Создать проект** в меню **Файл** .

2. В разделе **Проекты моделирования** диалогового окна **Новый проект**выберите пункт **Расширение проверки конструктора слоев**.

    Шаблон создает проект, который содержит небольшой пример.

   > [!WARNING]
   > Чтобы шаблон работал правильно, соблюдайте следующие рекомендации:
   >
   > - Отредактируйте вызовы функции `LogValidationError` , удалив необязательные аргументы `errorSourceNodes` и `errorTargetNodes`.
   > - Если вы используете пользовательские свойства, примените обновление, указанное в [Добавление пользовательских свойств в схемы зависимостей](../modeling/add-custom-properties-to-layer-diagrams.md).

3. Отредактируйте код, чтобы определить проверку. Более подробную информацию см. в разделе [Программная проверка](#programming).

4. Сведения о тестировании расширения см. в разделе [Отладка проверки слоев](#debugging).

   > [!NOTE]
   > Этот метод вызывается только в особых обстоятельствах. Точки останова не срабатывают автоматически. Более подробную информацию см. в разделе [Отладка проверки слоев](#debugging).

5. Чтобы установить расширение в основном экземпляре Visual Studio, или на другом компьютере, найдите *.vsix* файл *bin* каталога. Скопируйте его на компьютер, а затем дважды щелкните его. Чтобы удалить его, выберите **расширения и обновления** на **средства** меню.

## <a name="adding-a-layer-validator-to-a-separate-vsix"></a>Добавление проверяющего элемента слоя в отдельный файл VSIX

Если нужно создать один файл VSIX, который содержит проверяющие элементы слоев, команды и другие расширения, рекомендуется создать один проект для определения VSIX и отдельные проекты для обработчиков.

### <a name="to-add-layer-validation-to-a-separate-vsix"></a>Добавление проверки слоев в отдельный файл VSIX

1.  Создайте проект библиотеки классов в новом или существующем решении Visual Studio. В диалоговом окне **Новый проект** выберите пункт **Visual C#** , а затем **Библиотека классов**. Этот проект содержит класс проверки слоев.

2.  Определите или создайте проект VSIX в решении. Проект VSIX содержит файл с именем **source.extension.vsixmanifest**. Чтобы добавить проект VSIX, выполните указанные ниже действия.

    1.  В диалоговом окне **Новый проект** последовательно выберите пункты **Visual C#**, **Расширение среды**, **Проект VSIX**.

    2.  В контекстном меню проекта VSIX в **обозревателе решений**выберите пункт **Назначить запускаемым проектом**.

3.  В **source.extension.vsixmanifest**на вкладке **Активы**добавьте проект проверки слоев в качестве компонента MEF:

    1.  Выберите **Создать**.

    2.  В диалоговом окне **Добавить новый актив** установите следующие параметры:

         **Тип** = **Microsoft.VisualStudio.MefComponent**

         **Источник** = **Проект в текущем решении**

         **Проект** = *проект проверяющего элемента*

4.  Также необходимо добавить его в качестве проверки слоев:

    1.  Выберите **Создать**.

    2.  В диалоговом окне **Добавить новый актив** установите следующие параметры:

         **Тип** = **Microsoft.VisualStudio.ArchitectureTools.Layer.Validator**. Это значение не указано в раскрывающемся списке. Его необходимо ввести с клавиатуры.

         **Источник** = **Проект в текущем решении**

         **Проект** = *проект проверяющего элемента*

5.  Вернитесь в проект проверки слоев и добавьте указанные ниже ссылки на проект.

    |**Ссылки**|**Возможности**|
    |-|-|
    |Microsoft.VisualStudio.GraphModel.dll|Чтение графа архитектуры|
    |Microsoft.VisualStudio.ArchitectureTools.Extensibility.CodeSchema.dll|Чтение кода DOM, связанного со слоями|
    |Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.dll|Чтение модели слоев|
    |Microsoft.VisualStudio.ArchitectureTools.Extensibility|Чтение и обновление фигур и схем|
    |System.ComponentModel.Composition|Определение компонента проверки с помощью Managed Extensibility Framework (MEF)|
    |Microsoft.VisualStudio.Modeling.Sdk.[версия]|Определение расширений моделирования|

6.  Скопируйте пример кода в конце этого раздела в файл класса в проекте библиотеки проверяющего элемента, чтобы добавить в него код для проверки. Более подробную информацию см. в разделе [Программная проверка](#programming).

7.  Сведения о тестировании расширения см. в разделе [Отладка проверки слоев](#debugging).

    > [!NOTE]
    > Этот метод вызывается только в особых обстоятельствах. Точки останова не срабатывают автоматически. Более подробную информацию см. в разделе [Отладка проверки слоев](#debugging).

8.  Чтобы установить Расширение в основном экземпляре Visual Studio, или на другом компьютере, найдите **.vsix** файл **bin** каталог проекта VSIX. Скопируйте его на компьютер, где требуется выполнить установку VSIX. Дважды щелкните файл VSIX в проводнике Windows

     Чтобы удалить расширение, выберите пункт **Расширения и обновления** в меню **Сервис** .

##  <a name="programming"></a> Программная проверка

Чтобы определить расширение проверки слоя, необходимо определить класс указанным ниже образом.

- Общая форма объявления должна иметь следующий вид:

  ```csharp
  using System.ComponentModel.Composition;
  using Microsoft.VisualStudio.ArchitectureTools.Extensibility.CodeSchema;
  using Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer;
  using Microsoft.VisualStudio.GraphModel;
  ...
   [Export(typeof(IValidateArchitectureExtension))]
    public partial class Validator1Extension :
                    IValidateArchitectureExtension
    {
      public void ValidateArchitecture(Graph graph)
      {
         GraphSchema schema = graph.DocumentSchema;
        ...
    } }
  ```

- При обнаружении ошибки сообщите о ней с помощью функции `LogValidationError()`.

  > [!WARNING]
  > Не используйте необязательные параметры функции `LogValidationError`.

Когда пользователь вызывает команду меню **Проверить архитектуру** , система среды выполнения слоев анализирует слои и их артефакты и формирует граф. Граф состоит из четырех частей:

- Модели слоев решения Visual Studio, которые отображаются в виде узлов и ссылок в графе.

- код, элементы проекта и другие артефакты, определенные в решении и представленные в виде узлов, а также связи, которые представляют зависимости, обнаруженные в процессе анализа;

- связи между узлами слоя и узлами артефактов кода;

- узлы, представляющие ошибки, которые были обнаружены проверяющим элементом.

После создания графа вызывается стандартный метод проверки. После этого все установленные методы проверки расширения вызываются в произвольном порядке. Граф передается каждому методу `ValidateArchitecture` , который может просканировать его и сообщить об обнаруженных ошибках.

> [!NOTE]
> Это не так же, как процесс проверки, который может использоваться в предметно ориентированных языков.

Методы проверки не должны менять проверяемую модель слоев или код.

Модель графа определена в узле <xref:Microsoft.VisualStudio.GraphModel>. Основными классами этого узла являются <xref:Microsoft.VisualStudio.GraphModel.GraphNode> и <xref:Microsoft.VisualStudio.GraphModel.GraphLink>.

Каждый узел и каждая связь имеют одну или несколько категорий, задающих тип элемента или отношения, которое этот узел или связь представляет. Узлы типичного графа имеют следующие категории:

- Dsl.LayerModel

- Dsl.Layer

- Dsl.Reference

- CodeSchema_Type

- CodeSchema_Namespace

- CodeSchema_Type

- CodeSchema_Method

- CodeSchema_Field

- CodeSchema_Property

Связи от слоев к элементам в коде имеют категорию «Представляет».

##  <a name="debugging"></a> Отладка проверки

Чтобы выполнить отладку расширения проверки слоев, нажмите клавиши CTRL+F5. Откроется экспериментальный экземпляр Visual Studio. Откройте или создайте модель слоев в этом экземпляре. Эта модель должна быть связана с кодом и иметь хотя бы одну зависимость.

### <a name="test-with-a-solution-that-contains-dependencies"></a>Тестирование решения, содержащего зависимости

Проверка выполняется только при наличии указанных ниже характеристик.

- Имеется по крайней мере одна связь зависимости на схеме зависимостей.

- В модели имеются слои, связанные с элементами кода.

При первом запуске экспериментального экземпляра Visual Studio для тестирования расширения проверки, откройте или создайте это решение, которое имеет следующие характеристики.

### <a name="run-clean-solution-before-validate-architecture"></a>Выполнение очистки решения перед проверкой архитектуры

Всякий раз при обновлении кода проверки необходимо использовать команду **Очистить решение** в меню **Сборка** экспериментального решения. Только после этого можно тестировать команду «Проверка». Это связано с тем, что результаты проверки кэшируются. Если схема зависимостей теста или ее код не обновлялись, методы проверки не выполняются.

### <a name="launch-the-debugger-explicitly"></a>Явный запуск отладчика

Проверка выполняется в отдельном процессе. Поэтому точки останова используемого метода проверки не будут активированы. Необходимо явно подключить отладчик к процессу после запуска проверки.

Чтобы подключить отладчик к процессу проверки, вставьте вызов функции `System.Diagnostics.Debugger.Launch()` в начало метода проверки. Когда появится диалоговое окно отладки, выберите основной экземпляр Visual Studio.

Кроме того, можно вставить вызов функции `System.Windows.Forms.MessageBox.Show()`. Когда появится окно сообщения, перейдите в основной экземпляр Visual Studio и на **Отладка** выберите в меню пункты **присоединение к процессу**. Выберите процесс, который называется **Graphcmd.exe**.

Всегда запускайте экспериментальный экземпляр, нажимая клавиши CTRL+F5 (**Запуск без отладки**).

### <a name="deploying-a-validation-extension"></a>Развертывание расширения проверки

Чтобы установить расширение проверки на компьютер, на котором установлена подходящая версия Visual Studio, откройте VSIX-файл на конечном компьютере.

##  <a name="example"></a> Example code

```csharp
using System;
using System.ComponentModel.Composition;
using System.Globalization;
using System.Linq;
using System.Text.RegularExpressions;
using Microsoft.VisualStudio.ArchitectureTools.Extensibility.CodeSchema;
using Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer;
using Microsoft.VisualStudio.GraphModel;

namespace Validator3
{
    [Export(typeof(IValidateArchitectureExtension))]
    public partial class Validator3Extension : IValidateArchitectureExtension
    {
        /// <summary>
        /// Validate the architecture
        /// </summary>
        /// <param name="graph">The graph</param>
        public void ValidateArchitecture(Graph graph)
        {
            if (graph == null) throw new ArgumentNullException("graph");

            // Uncomment the line below to debug this extension during validation
            // System.Windows.Forms.MessageBox.Show("Attach 2 to GraphCmd.exe with process id " + System.Diagnostics.Process.GetCurrentProcess().Id);

            // Get all layers on the diagram
            foreach (GraphNode layer in graph.Nodes.GetByCategory("Dsl.Layer"))
            {
                System.Threading.Thread.Sleep(100);
                // Get the required regex property from the layer node
                string regexPattern = "^[a-zA-Z]+$"; //layer[customPropertyCategory] as string;
                if (!string.IsNullOrEmpty(regexPattern))
                {
                    Regex regEx = new Regex(regexPattern);

                    // Get all referenced types in this layer including those from nested layers so each
                    // type is validated against all containing layer constraints.
                    foreach (GraphNode containedType in layer.FindDescendants().Where(node => node.HasCategory("CodeSchema_Type")))
                    {
                        // Check the type name against the required regex
                        CodeGraphNodeIdBuilder builder = new CodeGraphNodeIdBuilder(containedType.Id, graph);
                        string typeName = builder.Type.Name;
                        if (!regEx.IsMatch(typeName))
                        {
                            // Log an error
                            string message = string.Format(CultureInfo.CurrentCulture, Resources.InvalidTypeNameMessage, typeName);
                            this.LogValidationError(graph, typeName + "TypeNameError", message, GraphErrorLevel.Error, layer);
                        }
                    }
                }

            }

        }
    }
}
```

## <a name="see-also"></a>См. также

- [Расширение схем зависимостей](../modeling/extend-layer-diagrams.md)
