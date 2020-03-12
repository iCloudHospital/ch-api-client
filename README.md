
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
