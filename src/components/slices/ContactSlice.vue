<template>
  <div class="row py-2 py-sm-2 py-md-3 py-lg-5">
      <div class="col-xxl-8 col-xl-12 col-lg-12 col-md-12 col-sm-12 mx-auto text-center">
        <form method="post">
          <div class="row">
            <div class="col-md-6">
                <div class="mb-3">
                    <input type="text" name="userName" class="form-control" placeholder="NAME" value="" required>
                </div>
                <select class="form-select mb-3" aria-label="Default select example">
                  <option selected>I'M A</option>
                  <option value="1">One</option>
                  <option value="2">Two</option>
                  <option value="3">Three</option>
                </select>
                <div class="mb-3">
                    <input type="text" name="userPhone" class="form-control" placeholder="TELEPHONE" value="" required>
                </div>
            </div>
            <div class="col-md-6 text-md-start">
                <div class="mb-3">
                    <input type="text" name="userEmail" class="form-control" placeholder="EMAIL" value="" required>
                </div>
                <div class="mb-3">
                    <input type="text" name="userCompany" class="form-control" placeholder="COMPANY (IF APPLICABLE)" value="">
                </div>
                <div class="mb-3">
                    <textarea name="userMsg" class="form-control" placeholder="MESSAGE" style="width: 100%; height: 150px;"></textarea>
                </div>
                <div class="mt-3">
                    <input type="submit" name="Submit" class="btn btn-circle" value="Submit">
                </div>
                <div class="mt-5">
                     <ul class="list-group list-group-flush text-start m-0 p-0">
                        <li class="list-group-item bg-transparent border-bottom-0 m-0 p-1 fm-pink">Email : <a class="text-decoration-none fm-black" href="tel:+068766773" ><em>06 8766773</em></a></li>
                        <li class="list-group-item bg-transparent border-bottom-0 m-0 p-1 fm-pink">Phone : <a class="text-decoration-none fm-black" href="mailto:webstore@thebrandoutlet.co.nz"><em>webstore@thebrandoutlet.co.nz</em></a></li>
                      </ul>
                </div>
            </div>
          </div>
        </form>
      </div>
  </div>
</template>

<script>
export default {
  props: ['slice'],
  name: 'contact-slice'
}
</script>

<style>
.form-control,.form-select {
  border:1px solid #5b146f;
}
.btn-circle {
  color: #5b146f;
  border:2px solid #5b146f;
  border-radius: 48px;
  padding: 10px 100px;
}
.btn-circle:hover {
  color: #fff;
  border:2px solid #fff;
  background: #5b146f;
}
</style>