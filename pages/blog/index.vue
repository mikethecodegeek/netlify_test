<template>

  <div>
<html lang="en">

    <body>
        <div id="layoutDefault">
            <div id="layoutDefault_content">
                <main>
                  <Nav/>
                    <!-- Page Header-->
                    <header class="page-header-ui page-header-ui-dark bg-img-cover overlay overlay-60" style="background-image: url(https://source.unsplash.com/PTRzqc_h1r4/1600x900)">
                        <div class="page-header-ui-content position-relative">
                            <div class="container px-5 text-center">
                                <div class="row gx-5 justify-content-center">
                                    <div class="col-lg-8">
                                        <h1 class="page-header-ui-title mb-3">Publications</h1>
                                        <p class="page-header-ui-text mb-0">Browse articles, keep up to date, and learn more on our blog!</p>
                                    </div>
                                </div>
                            </div>
                        </div>
                        <div class="svg-border-rounded text-light">
                            <!-- Rounded SVG Border-->
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 144.54 17.34" preserveAspectRatio="none" fill="currentColor"><path d="M144.54,17.34H0V0H144.54ZM0,0S32.36,17.34,72.27,17.34,144.54,0,144.54,0"></path></svg>
                        </div>
                    </header>
                     
                     
                    <section class="bg-light py-10">
                        <div class="container px-5">
                            <nuxt-link :to="`blog/test`" class="card post-preview post-preview-featured lift mb-5 overflow-hidden">
                                <div class="row g-0">
                                    <div class="col-lg-5"><div class="post-preview-featured-img" style="background-image: url('https://source.unsplash.com/vZJdYl5JVXY/660x360')"></div></div>
                                    <div class="col-lg-7">
                                        <div class="card-body">
                                            <div class="py-5">
                                                <h5 class="card-title">Title</h5>
                                                <p class="card-text">description</p>
                                            </div>
                                            <hr />
                                            <div class="post-preview-meta">
                                                <img class="post-preview-meta-img" src="assets/img/illustrations/profiles/profile-1.png" />
                                                <div class="post-preview-meta-details">
                                                    <div class="post-preview-meta-details-name">Valerie Luna</div>
                                                    <div class="post-preview-meta-details-date">Feb 5 &middot; 6 min read</div>
                                                </div>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </nuxt-link>
                            <div class="row gx-5">
                            <ul v-for="(blogPost, index) in blogPosts" :key="index">
                                <div class="col-md-6 col-xl-4 mb-5">
                                    <nuxt-link :to="`/blog/${blogPost.slug}`" class="card post-preview lift h-100">
                                        <img class="card-img-top" src="https://source.unsplash.com/KE0nC8-58MQ/660x360" alt="..." />
                                        <div class="card-body">
                                            <h5 class="card-title">{{blogPost.title}}</h5>
                                            <p class="card-text">{{blogPost.description}}</p>
                                        </div>
                                        <div class="card-footer">
                                            <div class="post-preview-meta">
                                                <img class="post-preview-meta-img" src="assets/img/illustrations/profiles/profile-2.png" />
                                                <div class="post-preview-meta-details">
                                                    <div class="post-preview-meta-details-name">Aariz Fischer</div>
                                                    <div class="post-preview-meta-details-date">Feb 4 &middot; 5 min read</div>
                                                </div>
                                            </div>
                                        </div>
                                    </nuxt-link>
                                </div>
                              </ul>

                            </div>
                            <nav aria-label="Page navigation example">
                                <ul class="pagination pagination-blog justify-content-center">
                                    <li class="page-item disabled">
                                        <a class="page-link" href="#!" aria-label="Previous"><span aria-hidden="true">«</span></a>
                                    </li>
                                    <li class="page-item active"><a class="page-link" href="#!">1</a></li>
                                    <li class="page-item"><a class="page-link" href="#!">2</a></li>
                                    <li class="page-item"><a class="page-link" href="#!">3</a></li>
                                    <li class="page-item disabled"><a class="page-link" href="#!">...</a></li>
                                    <li class="page-item"><a class="page-link" href="#!">12</a></li>
                                    <li class="page-item">
                                        <a class="page-link" href="#!" aria-label="Next"><span aria-hidden="true">»</span></a>
                                    </li>
                                </ul>
                            </nav>
                        </div>
                      
                    </section>
                </main>
            </div>
          <Footer/>
        </div>
        <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/js/bootstrap.bundle.min.js" crossorigin="anonymous"></script>
        <script src="js/scripts.js"></script>
    </body>
</html>
   
  </div>
   
</template>


<script>
import Logo from '~/components/Logo.vue'
import Nav from '~/components/Nav.vue'
import Footer from '~/components/Footer.vue'

export default {
  components: {
    Logo, Nav, Footer
  },
  head() {
    return {
      link: [],
      script: [
        { src: 'https://identity.netlify.com/v1/netlify-identity-widget.js' }
      ]
    }
  },
  computed: {
    blogPosts() {
      return this.$store.state.blogPosts
    }
  }
}
</script>