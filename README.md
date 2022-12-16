# catatan Ulak Ulik
# fungsi use efect untuk melakukan fetching data pada sisi client <br>
 https://nextjs.org/docs/basic-features/data-fetching/client-side <br>
const [data, setData] = useState(null)
 useEffect(() => {
    setLoading(true)
    fetch('/api/profile-data')
      .then((res) => res.json())
      .then((data) => {
        setData(data)
        setLoading(false)
      })
  }, [])
  ## How install dbeaver di ubuntu
  https://www.how2shout.com/linux/3-ways-to-install-dbeaver-ubuntu-22-04-lts-jammy-linux/
  ## Vpn ubuntu
  `sudo apt-get install openconnect network-manager-openconnect network-manager-openconnect-gnome`
  
  ## DATA TABLE NEXT JS
  https://gridjs.io/docs/examples/search?mibextid=t3LuGO
## Remove Dpkg
`sudo apt-get remove randompackage`

# tutorial docker ubuntu
https://www.youtube.com/watch?v=Vplj9b0L_1Y
 ## install nodejs ubuntu
 https://www.youtube.com/watch?v=3hzShQSrIy8

## react + docker
https://www.youtube.com/watch?v=3xDAU5cvi5E <br>

#### build image.
 `docker build -t react-image`. 
#### cek image.
`docker imgae -ls` 
#### run container.
`docker run -e CHOKIDAR_USEPOLLING=true -v $(pwd)/src:/app/src -d -p 3000:3000 --name react-app react-image`
#### remove container.
`docker rm react-app -f` 
#### cek container yang berjalan
`docker ps`

## postgree
https://www.cherryservers.com/blog/how-to-install-and-setup-postgresql-server-on-ubuntu-20-04

## migrate fk
`exports.up = function (knex) {
    return knex.schema.createTable('_ubis', (table) => {
      table.increments();
      table.string('name');
      table.integer('flag');
      table.timestamps(true, true);
    });
  };
  
  exports.down = function (knex) {
    return knex.schema.dropTable('_ubis');
  };`



  
  ## fk dari table di atas
  `exports.up = function (knex) {
    return knex.schema.createTable('_sub_ubis', (table) => {
      table.increments();
      table.integer('ubis_id');
      table.string('name');
      table.integer('flag');
      table.integer('status');
      table.string('updated_by');
      table.timestamps(true, true);
    
      table.foreign('ubis_id') 
        .withKeyName('ubis_fk')
        .references('id')
        .inTable('_ubis')
        .onUpdate('CASCADE')
        .onDelete('SET NULL');
    });
  };
  exports.down = function (knex) {
    return knex.schema.dropTable('_sub_ubis');
  };`
  
  `table.foreign('ubis_id')` adalah kolom utuk fk 
  `.withKeyName('ubis_fk')` adalah name fk bebas
  `.references('id')` referance merupakan kolom maping yang ada di table mappingnya
  `.inTable('_ubis')` in table ini merupakan table join
  
