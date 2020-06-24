
//    public MongoDBService() {
//        mongo = new MongoClient(
//            "localhost",
//            27017
//            );
//        credential = MongoCredential.createCredential(
//                "Admin",
//                "gateKeeper",
//                "Admin123".toCharArray()
//        );
//        database = mongo.getDatabase("gateKeeper");
//        System.out.println("connected to the database successfully");
//        SocietyConfigCollection = database.getCollection("SocietyConfig");
//    }
//
//    public String registerNewSociety(SocietyConfig registrationDetails){
//        try{
//            String jsonObj = JSON.parse(mapper.writeValueAsString(registrationDetails)).toString();
//            SocietyConfigCollection.insertOne(Document.parse(jsonObj));
//            ObjectId id = (ObjectId) SocietyConfigCollection.find(Filters.eq("name",registrationDetails.getName())).first().get("_id");
//            String SocietyId = "Society"+id.toString();
//            database.createCollection(SocietyId);
//            return SocietyId;
//        } catch (Exception e){
//            return "ERROR!";
//        }
//    }
