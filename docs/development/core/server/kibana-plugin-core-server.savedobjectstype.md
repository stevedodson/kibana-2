<!-- Do not edit this file. It is automatically generated by API Documenter. -->

[Home](./index.md) &gt; [kibana-plugin-core-server](./kibana-plugin-core-server.md) &gt; [SavedObjectsType](./kibana-plugin-core-server.savedobjectstype.md)

## SavedObjectsType interface


<b>Signature:</b>

```typescript
export interface SavedObjectsType<Attributes = any> 
```

## Properties

|  Property | Type | Description |
|  --- | --- | --- |
|  [convertToAliasScript?](./kibana-plugin-core-server.savedobjectstype.converttoaliasscript.md) | string | <i>(Optional)</i> If defined, will be used to convert the type to an alias. |
|  [convertToMultiNamespaceTypeVersion?](./kibana-plugin-core-server.savedobjectstype.converttomultinamespacetypeversion.md) | string | <i>(Optional)</i> If defined, objects of this type will be converted to a 'multiple' or 'multiple-isolated' namespace type when migrating to this version.<!-- -->Requirements:<!-- -->1. This string value must be a valid semver version 2. This type must have previously specified [\`namespaceType: 'single'\`](./kibana-plugin-core-server.savedobjectsnamespacetype.md) 3. This type must also specify [\`namespaceType: 'multiple'\`](./kibana-plugin-core-server.savedobjectsnamespacetype.md) \*or\* [\`namespaceType: 'multiple-isolated'\`](./kibana-plugin-core-server.savedobjectsnamespacetype.md)<!-- -->Example of a single-namespace type in 7.12:
```ts
{
  name: 'foo',
  hidden: false,
  namespaceType: 'single',
  mappings: {...}
}
```
Example after converting to a multi-namespace (isolated) type in 8.0:
```ts
{
  name: 'foo',
  hidden: false,
  namespaceType: 'multiple-isolated',
  mappings: {...},
  convertToMultiNamespaceTypeVersion: '8.0.0'
}
```
Example after converting to a multi-namespace (shareable) type in 8.1:
```ts
{
  name: 'foo',
  hidden: false,
  namespaceType: 'multiple',
  mappings: {...},
  convertToMultiNamespaceTypeVersion: '8.0.0'
}
```
Note: migration function(s) can be optionally specified for any of these versions and will not interfere with the conversion process. |
|  [excludeOnUpgrade?](./kibana-plugin-core-server.savedobjectstype.excludeonupgrade.md) | SavedObjectTypeExcludeFromUpgradeFilterHook | <i>(Optional)</i> If defined, allows a type to exclude unneeded documents from the migration process and effectively be deleted. See [SavedObjectTypeExcludeFromUpgradeFilterHook](./kibana-plugin-core-server.savedobjecttypeexcludefromupgradefilterhook.md) for more details. |
|  [hidden](./kibana-plugin-core-server.savedobjectstype.hidden.md) | boolean | Is the type hidden by default. If true, repositories will not have access to this type unless explicitly declared as an <code>extraType</code> when creating the repository.<!-- -->See [createInternalRepository](./kibana-plugin-core-server.savedobjectsservicestart.createinternalrepository.md)<!-- -->. |
|  [indexPattern?](./kibana-plugin-core-server.savedobjectstype.indexpattern.md) | string | <i>(Optional)</i> If defined, the type instances will be stored in the given index instead of the default one. |
|  [management?](./kibana-plugin-core-server.savedobjectstype.management.md) | SavedObjectsTypeManagementDefinition&lt;Attributes&gt; | <i>(Optional)</i> An optional [saved objects management section](./kibana-plugin-core-server.savedobjectstypemanagementdefinition.md) definition for the type. |
|  [mappings](./kibana-plugin-core-server.savedobjectstype.mappings.md) | SavedObjectsTypeMappingDefinition | The [mapping definition](./kibana-plugin-core-server.savedobjectstypemappingdefinition.md) for the type. |
|  [migrations?](./kibana-plugin-core-server.savedobjectstype.migrations.md) | SavedObjectMigrationMap \| (() =&gt; SavedObjectMigrationMap) | <i>(Optional)</i> An optional map of [migrations](./kibana-plugin-core-server.savedobjectmigrationfn.md) or a function returning a map of [migrations](./kibana-plugin-core-server.savedobjectmigrationfn.md) to be used to migrate the type. |
|  [name](./kibana-plugin-core-server.savedobjectstype.name.md) | string | The name of the type, which is also used as the internal id. |
|  [namespaceType](./kibana-plugin-core-server.savedobjectstype.namespacetype.md) | SavedObjectsNamespaceType | The [namespace type](./kibana-plugin-core-server.savedobjectsnamespacetype.md) for the type. |
|  [schemas?](./kibana-plugin-core-server.savedobjectstype.schemas.md) | SavedObjectsValidationMap \| (() =&gt; SavedObjectsValidationMap) | <i>(Optional)</i> An optional schema that can be used to validate the attributes of the type.<!-- -->When provided, calls to [create](./kibana-plugin-core-server.savedobjectsclient.create.md) will be validated against this schema.<!-- -->See [SavedObjectsValidationMap](./kibana-plugin-core-server.savedobjectsvalidationmap.md) for more details. |

