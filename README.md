
usage:


import { CountriesApi, CountryItemViewModel } from './out/api';
import { Configuration } from './out/configuration';

const models :CountryItemViewModel[] = [];

const config = new Configuration({
  basePath: 'https://api-int.icloudhospital.com/'
});
let result = new CountriesApi(config)
  .apiV1CountriesGet()
  .then(d => console.log(d.data.items.map(t => t.name)));
!!!

!!! update openapi-generator to beta2
npm install @openapitools/openapi-generator-cli@cli-5.0.0-beta2 -g

openapi-generator-cli generate -g typescript-axios -o src -i https://api-int.icloudhospital.com/swagger/v1/swagger.json --skip-validate-spec --type-mappings=DateTime=Date
npx tsc