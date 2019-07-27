# API : Zallow General Description Service
    * Read / GET - read an item
    `/houses/*`
    This route fetches the house at the requested id.
    The most used route.

  
    // Delete / DELETE - delete an item
    `/houses/delete/*`
    This route deletes the house at the requested id.

    // Update / PUT - update an item
    `/houses/update/*`
    This route updates the house at the requested id.

    // Create / POST - create a new item
    `/houses/create/`
    This route fetches the house with the next available id `AUTO INCREMENT`.