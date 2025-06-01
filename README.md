# mongo2_med
<pre>
  db.products.aggregate([
  {
    $group: {
      _id: "$supplier.name",      
      total_quantity: { $sum: "$quantity" }  
    }
  }
])
{
  _id: 'StyleCraft',
  total_quantity: 120
}
{
  _id: 'GadgetPro',
  total_quantity: 125
}
{
  _id: 'FashionHub',
  total_quantity: 280
}
{
  _id: 'HomeBest',
  total_quantity: 30
}
{
  _id: 'ActiveLife',
  total_quantity: 90
}
{
  _id: 'SoundWave',
  total_quantity: 60
}
{
  _id: 'TechGlobe',
  total_quantity: 60
}
db.products.aggregate([
  {
    $unwind: "$tags"  
  },
  {
    $group: {
      _id: "$tags",                      
      average_price: { $avg: "$price" }  
    }
  },
  {
    $sort: { average_price: -1 } 
  }
])
{
  _id: 'work',
  average_price: 1200
}
{
  _id: 'portable',
  average_price: 493
}
{
  _id: 'computer',
  average_price: 433.3333333333333
}
{
  _id: 'coffee',
  average_price: 250
}
{
  _id: 'appliance',
  average_price: 250
}
{
  _id: 'kitchen',
  average_price: 250
}
{
  _id: 'gadget',
  average_price: 199
}
{
  _id: 'wearable',
  average_price: 199
}
{
  _id: 'audio',
  average_price: 80
}
{
  _id: 'mechanical',
  average_price: 75
}
{
  _id: 'denim',
  average_price: 60
}
{
  _id: 'wireless',
  average_price: 52.5
}
{
  _id: 'peripheral',
  average_price: 50
}
{
  _id: 'leather',
  average_price: 45
}
{
  _id: 'fashion',
  average_price: 45
}
{
  _id: 'clothing',
  average_price: 40
}
{
  _id: 'fitness',
  average_price: 30
}
{
  _id: 'exercise',
  average_price: 30
}
{
  _id: 'casual',
  average_price: 20
}
{
  _id: 'cotton',
  average_price: 20
}
db.products.aggregate([
  {
    $match: {
      date_added: {
        $gte: new Date("2023-02-01T00:00:00Z"),
        $lt: new Date("2023-03-01T00:00:00Z")
      }
    }
  },
  {
    $project: {
      _id: 0,
      name: 1,
      category: 1,
      date_added: {
        $dateToString: {
          format: "%Y-%m-%d",
          date: "$date_added"
        }
      }
    }
  }
])
{
  name: 'Wireless Mouse',
  category: 'Electronics',
  date_added: '2023-02-01'
}
{
  name: 'Espresso Machine',
  category: 'Home Goods',
  date_added: '2023-02-15'
}
{
  name: 'Bluetooth Speaker',
  category: 'Electronics',
  date_added: '2023-02-25'
}
Atlas atlas-pyia45-shard-0 [primary] products


</pre>
