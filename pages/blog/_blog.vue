<template>
<div>

    <head>
        <meta charset="utf-8" />
        <meta http-equiv="X-UA-Compatible" content="IE=edge" />
        <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no" />
        <meta name="description" content="" />
        <meta name="author" content="" />
        <title>Blog Post - SB UI Kit Pro</title>
        <link href="css/styles.css" rel="stylesheet" />
        <link rel="icon" type="image/x-icon" href="assets/img/favicon.png" />
        <script data-search-pseudo-elements defer src="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.1.1/js/all.min.js" crossorigin="anonymous"></script>
        <script src="https://cdnjs.cloudflare.com/ajax/libs/feather-icons/4.24.1/feather.min.js" crossorigin="anonymous"></script>
    </head>
    <body>
        <div id="layoutDefault">
            <div id="layoutDefault_content">
                <main>
                    <!-- Navbar-->
                  <Nav/>
                    <section class="bg-light py-10">
                        
                        <div class="container px-5">
                            <div class="row gx-5 justify-content-center">
                                <div class="col-lg-10 col-xl-8">
                                    <div class="single-post">
                                        <h1>{{blogPost.title}}</h1>
                                        <p class="lead">{{blogPost.description}}</p>
                                        <div class="d-flex align-items-center justify-content-between mb-5">
                                            <div class="single-post-meta me-4">
                                                <img class="single-post-meta-img" src="assets/img/illustrations/profiles/profile-1.png" />
                                                <div class="single-post-meta-details">
                                                    <div class="single-post-meta-details-name">Valerie Luna</div>
                                                    <div class="single-post-meta-details-date">Feb 5 &middot; 6 min read</div>
                                                </div>
                                            </div>
                                            <div class="single-post-meta-links">
                                                <a href="#!"><i class="fab fa-twitter fa-fw"></i></a>
                                                <a href="#!"><i class="fab fa-facebook-f fa-fw"></i></a>
                                                <a href="#!"><i class="fas fa-bookmark fa-fw"></i></a>
                                            </div>
                                        </div>
                                        <img class="img-fluid mb-2 rounded" src="https://source.unsplash.com/vZJdYl5JVXY/990x540" />
                                        <div class="small text-gray-500 text-center">Photo Credit: Unsplash</div>
                                        <div class="single-post-text my-5">
                                           <div v-html="$md.render(blogPost.body)" />
                                            <hr class="my-5" />
                                            <div class="text-center"><a class="btn btn-transparent-dark" href="page-blog-overview.html">Back to Blog Overview</a></div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>

                        
                        <div class="svg-border-rounded text-dark">
                            <!-- Rounded SVG Border-->
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 144.54 17.34" preserveAspectRatio="none" fill="currentColor"><path d="M144.54,17.34H0V0H144.54ZM0,0S32.36,17.34,72.27,17.34,144.54,0,144.54,0"></path></svg>
                        </div>
                    </section>

                  <Footer/>

                </main>
            </div>

           
        </div>
        <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/js/bootstrap.bundle.min.js" crossorigin="anonymous"></script>
        <script src="js/scripts.js"></script>
    </body>
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
  },
    async asyncData({ params, payload }) {
    if (payload) return { blogPost: payload }
    else
      return {
        blogPost: await require(`~/assets/content/blog/${params.blog}.json`)
      }
  }
}
</script>