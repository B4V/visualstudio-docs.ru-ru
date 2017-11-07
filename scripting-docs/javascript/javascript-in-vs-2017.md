---
title: "JavaScript в Visual Studio | Документация Майкрософт"
ms.custom: 
ms.date: 04/10/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 74dca14c-5071-416f-a92b-d09f95e3dfb8
caps.latest.revision: 1
author: bowdenk7
ms.author: wilkelly
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 29eb97427c2c5a29ee9a66e8e2a85953fd797efd
ms.openlocfilehash: d217443ed0231d71f861ed54b27f3f8d1e8d49ac
ms.contentlocale: ru-ru
ms.lasthandoff: 08/11/2017

---
# <a name="javascript-in-includevsdev15docsmiscincludesvsdev15mdmd"></a>JavaScript в [!include[vs_dev15](../../docs/misc/includes/vs_dev15_md.md)]

JavaScript — полноправный язык в Visual Studio. При написании кода JavaScript в интегрированной среде разработки Visual Studio можно использовать большинство или все стандартные средства редактирования (фрагменты кода, IntelliSense и т. д.). Код JavaScript можно написать для многих типов приложений и служб.

## <a name="ES6"></a> Поддержка ECMAScript 2015 (ES6) и более поздних версий
Visual Studio теперь поддерживает синтаксис обновлений языка ECMAScript, таких как ECMAScript 2015/2016.

### <a name="what-is-ecmascript-2015"></a>Что такое ECMAScript 2015?

Язык программирования JavaScript по-прежнему развивается, и за его обновления отвечает комитет [TC39](http://www.ecma-international.org/memento/TC39.htm).  
ECMAScript 2015 — обновление языка JavaScript, которое предоставляет множество новых полезных изменений синтаксиса и функций.
Подробное описание функций ES6 см. на [этом](http://es6-features.org) справочном сайте.

Наряду с ECMAScript 2015 среда Visual Studio также поддерживает ECMAScript 2016 и будет поддерживать будущие версии ECMAScript по мере их выпуска. Чтобы следить за работой комитета TC39 и последними изменениями в ECMAScript, заходите на их страницу в [GitHub](https://github.com/tc39).

### <a name="transpiling-javascript"></a>Транскомпиляция JavaScript

При использовании JavaScript часто возникает следующая проблема: вы хотите применять новейшие функции языка ES6+ для более эффективной работы, но среды выполнения (или часто браузеры) пока еще их не поддерживают.
Это означает, что вам нужно либо следить за тем, какие функции поддерживаются в разных браузерах (что может быть очень утомительно), либо преобразовывать код ES6+ в версию, поддерживаемую вашими целевыми средами выполнения (обычно это версия ES5).
Это часто называется "транскомпиляцией".

Одна из ключевых возможностей TypeScript — возможность транскомпиляции кода ES6+ в код ES5 или ES3. Она обеспечивает максимально эффективное создание кода, который при этом будет запускаться на любой платформе.  
Так как JavaScript в [!include[vs_dev15](../../docs/misc/includes/vs_dev15_md.md)] использует ту же языковую службу, что и TypeScript, в JavaScript также можно применять транскомпиляцию ES6+ в ES5.

Перед соответствующей настройкой нужно разобраться в доступных параметрах конфигурации. TypeScript настраивается с помощью файла `tsconfig.json`. При отсутствии такого файла используются значения по умолчанию. Для обеспечения совместимости эти значения по умолчанию отличаются, если присутствуют только файлы JavaScript (и, возможно, файлы `.d.ts`). Для компиляции файлов JavaScript нужно добавить файл `tsconfig.json`, а затем явным образом задать некоторые из этих параметров.

Ниже описаны обязательные параметры для файла tsconfig:

 - `allowJs`: это значение должно быть равно `true` для распознавания файлов JavaScript.
По умолчанию оно равно `false`, так как TypeScript компилируется в JavaScript, кроме того, это не позволяет компилятору включать только что скомпилированные файлы.
 - `outDir`: в этом параметре нужно задать расположение, не включенное в проект, чтобы выдаваемые файлы JavaScript не обнаруживались и не включались в проект (см. `exclude` ниже).
 - `module`: при использовании модулей этот параметр указывает компилятору, какой формат модулей должен использовать создаваемый код (например, `commonjs` для узла или средств увязки в пакеты, таких как Browserify).
 - `exclude`: этот параметр указывает папки, которые не нужно включать в проект. 
 В него следует добавить выходное расположение, а также не относящиеся к проекту папки, такие как `node_modules` или `temp`.
 - `enableAutoDiscovery`: этот параметр включает автоматическое обнаружение и скачивание файлов определений, как описано выше.
 - `compileOnSave`: этот параметр указывает компилятору, следует ли повторять компиляцию при каждом сохранении файла исходного кода в Visual Studio.
 - `typeAcquisition`: этот набор параметров управляет автоматическим получением типа (подробнее см. в [этом разделе](https://docs.microsoft.com/en-us/visualstudio/ide/javascript-intellisense#Auto)).

Чтобы преобразовать файлы JavaScript в модули CommonJS и поместить их в папку `./out`, можно использовать следующий файл `tsconfig.json`.

```json
{
  "compilerOptions": {
    "module": "commonjs",
    "allowJs": true,
    "outDir": "out"
  },
  "exclude": [
    "node_modules",
    "wwwroot",
    "out"
  ],
  "compileOnSave": true,
  "typeAcquisition": {
    "enable": true
  }
}
```

Предположим, параметры выше заданы и существовал исходный файл (`./app.js`), который включал несколько функций языка ECMAScript 2015, как показано ниже:

```js
import {Subscription} from 'rxjs/Subscription';  // ES6 import

class Foo {  // ES6 Class
    sayHi(name) {
        return `Hi ${name}, welcome to Salsa!`;  // ES6 template string
    }
}

export let sqr = x => x * x;  //ES6 export, let, and arrow function
export default Subscription;  //ES6 default export
```

Затем файл будет выдан в `./out/app.js`, нацеленный на ECMAScript 5 (по умолчанию), что выглядит примерно следующим образом:

```js
"use strict";
var Subscription_1 = require('rxjs/Subscription');
var Foo = (function () {
    function Foo() {
    }
    Foo.prototype.sayHi = function (name) {
        return "Hi " + name + ", welcome to Salsa!";
    };
    return Foo;
}());
exports.sqr = function (x) { return x * x; };
Object.defineProperty(exports, "__esModule", { value: true });
exports.default = Subscription_1.Subscription;
```

## <a name="better-intellisense"></a>Улучшенная поддержка IntelliSense

IntelliSense для JavaScript в [!include[vs_dev15](../../docs/misc/includes/vs_dev15_md.md)] теперь отображает гораздо больше информации в списках элементов и параметров. Эта новая информация предоставляется языковой службой TypeScript, которая использует статический анализ, чтобы помочь вам лучше понять код. Дополнительные сведения об улучшении технологии IntelliSense см. [здесь](/visualstudio/ide/javascript-intellisense/).

## <a name="JSX"></a> Поддержка синтаксиса JSX

JavaScript в [!include[vs_dev15](../../docs/misc/includes/vs_dev15_md.md)] обладает обширной поддержкой синтаксиса JSX. JSX — это набор синтаксиса, позволяющий использовать HTML-теги в файлах JavaScript. 

На приведенном ниже рисунке показан определенный в файле `comps.tsx` TypeScript компонент React, который затем используется из файла `app.jsx` с применением IntelliSense для завершений и документации в выражениях JSX.
TypeScript здесь не требуется, просто этот конкретный пример содержит некоторый объем кода TypeScript.

<img src="./media/react.png" height="500" width="640"/>

> [!NOTE]
> Для преобразования синтаксиса JSX вызовы React нужно добавить параметр `"jsx": "react"` в `compilerOptions` в указанном выше файле `tsconfig.json`.

Файл JavaScript, созданный в "./out/app.js" при сборке, будет содержать этот код:

```js
"use strict";
var comps_1 = require('./comps');
var x = React.createElement(comps_1.RepoDisplay, {description: "test"});
```

# <a name="configuring-your-javascript-project"></a>Настройка проекта JavaScript
Служба языка основана на статическом анализе. Это означает, что для получения результатов IntelliSense и других функций редактирования эта служба анализирует исходный код, не выполняя его.
Поэтому чем больше файлов включено в контекст проекта и чем больше их размер, тем больше памяти и ресурсов процессора будет использоваться во время анализа.
В связи с этим в отношении структуры вашего проекта по умолчанию делается ряд допущений:

- `package.json` и `bower.json` возвращают список зависимостей, используемых проектом, и по умолчанию включены в автоматическое получение типов <TODO: добавить ссылку>
- Папка верхнего уровня `node_modules` содержит исходный код библиотеки, и ее содержимое по умолчанию исключено из контекста проекта.
- Все остальные файлы `.js`, `.jsx`, `.ts` и `.tsx` могут являться *вашими собственными* исходными файлами и должны быть включены в контекст проекта.

В большинстве случаев для оптимальной работы достаточно будет просто открыть проект и использовать для него приведенную выше конфигурацию по умолчанию.
Однако в проектах с другой структурой папок или в больших проектах может иметь смысл более точная настройка языковой службы для анализа только ваших собственных исходных файлов.

## <a name="overriding-defaults"></a>Переопределение параметров по умолчанию
Чтобы переопределить приведенную выше конфигурацию по умолчанию, добавьте файл `tsconfig.json` в корневой каталог проекта.
Файл `tsconfig.json` имеет ряд параметров, позволяющих управлять контекстом проекта.
Некоторые из них перечислены ниже. Полный список всех доступных параметров [см. в хранилище схем](http://json.schemastore.org/tsconfig). 

## <a name="important-tsconfigjson-options"></a>Важные параметры `tsconfig.json`

```json
{
  "compilerOptions": {
    "allowJs": true,          // include .js and .jsx in project context (defaults to only .ts and .tsx)
    "noEmit": true            // turns off downlevel compiler
  },
  "files": [],                // list of explicit files to include in the project context. Highest priority.
  "include": [],              // list of folders or glob patterns to include in the project context.
  "exclude": [],              // list of folders or glob patterns to exclude. Overridden by files array.
  "typeAcquisition": {
    "enable": true,           // Defaulted to "false" with a tsconfig. Enables better IntelliSense in JS.
    "include": [ "jquery" ],  // Specific libs to fetch .d.ts files that weren't picked up by ATA 
    "exclude": [ "node" ]     // Specific libs to not fetch .d.ts files for
  }
}
```

## <a name="example-project-configuration"></a>Пример конфигурации проекта

Предположим, что у нас есть проект со следующей конфигурацией:
- Исходные файлы проекта находятся в папке `wwwroot/js`
- Файлы библиотек проекта находятся в папке `wwwrrot/lib`
- `bootstrap`, `jquery`, `jquery-validation` и `jquery-validation-unobtrusive` указаны в `bower.json`
- Инструменты `kendo-ui` вручную добавлены в папку библиотеки

![Структура папок](./media/folderStructure.png)

Чтобы языковая служба анализировала только ваши исходные файлы в папке `js`, но при этом получала и использовала файлы `.d.ts` для библиотек в папке `lib`, вы можете использовать следующую конфигурацию `tsconfig.json`.

```json
{
  "compilerOptions": {
    "allowJs": true,          
    "noEmit": true            
  },
  "exclude": ["wwwroot/lib"],  //ignore lib folders, we will get IntelliSense via ATA
  "typeAcquisition": {
    "enable": true,            
    "include": [ "kendo-ui" ]  //kendo-ui wasn't added via bower, so we need to list it here
  }
}
```

# <a name="notable-changes-from-vs-2015"></a>Важные изменения по сравнению с VS 2015 
Так как в [!include[vs_dev15](../../docs/misc/includes/vs_dev15_md.md)] используется совершенно новая служба языка, в некоторых случаях ее поведение будет отличаться от предыдущих версий.
Наиболее существенные изменения: замена VSDoc на JSDoc, удаление особых расширений `.intellisense.js` и ограниченный набор функций IntelliSense для некоторых шаблонов кода.

## <a name="no-more-references-or-referencesjs"></a>Больше не используются `///<references/>` и `_references.js`
Раньше было довольно сложно понять, какие файлы входят в область IntelliSense в конкретный момент времени.
Иногда желательно было включить в область все ваши файлы, иногда нет, но для этого нужны были сложные конфигурации, в которых требовалось контролировать ссылки вручную.
Теперь вам больше не нужно думать об управлении ссылками, ставить к ссылкам комментарии с тремя косыми чертами и создавать файлы `_references.js`.

Дополнительные сведения о работе IntelliSense см. на странице [IntelliSense для JavaScript](/visualstudio/ide/javascript-intellisense/).

## <a name="vsdoc"></a>VSDoc
Комментарии к XML-документации (иногда называемые VSDoc) в прошлом можно было использовать для добавления в исходный код вспомогательных данных в дополнение к результатам IntelliSense.
Теперь VSDoc больше не поддерживаются и вместо них используется принятый для JavaScript стандарт [JSDoc](http://usejsdoc.org/about-getting-started.html) с более удобным синтаксисом.

### <a name="intellisensejs-extensions"></a>Расширения `.intellisense.js`
Ранее вы могли создавать [расширения IntelliSense](https://msdn.microsoft.com/en-us/library/hh874692.aspx), которые позволяли добавлять ваши собственные результаты завершения для сторонних библиотек.
Разрабатывать эти расширения было довольно сложно, а устанавливать их и ссылаться на них — неудобно, поэтому новая языковая служба больше не поддерживает эти файлы.
В качестве более простой альтернативы вы можете написать файл определения TypeScript, который обеспечит все те же возможности для IntelliSense, которые раньше предлагались расширениями `.intellisense.js`.
Дополнительные сведения о создании файлов объявлений (`.d.ts`) см. [здесь](http://www.typescriptlang.org/docs/handbook/declaration-files/introduction.html).

### <a name="unsupported-patterns"></a>Неподдерживаемые шаблоны
Поскольку новая языковая служба основана на статическом анализе, а не на механизме выполнения (сведения о различиях см. в [этой статье](https://github.com/Microsoft/TypeScript/issues/4789)), некоторые шаблоны JavaScript больше не могут быть обнаружены.
Наиболее распространенным является шаблон "expando". Сейчас языковая служба не предоставляет данные IntelliSense по объектам, к которым приписываются свойства после объявления.
Пример:

```js
var obj = {};
obj.a = 10;
obj.b = "hello world";
obj. // IntelliSense won't show properties a or b
```

Это можно обойти, объявив свойства при создании объекта:
```js
var obj = {
    "a": 10,
    "b": "hello world"
}
obj. // IntelliSense shows properties a and b
```

Вы также можете добавить комментарий JSDoc, как показано выше:
```js
/**
 * @type {{a: number, b: string}}
 */
var obj = {};
obj.a = 10;
obj.b = "hello world";
obj. // IntelliSense shows properties a and b
```