# Gate-policy-
*********************************************************************
*****************************************************************************
*************************************************************************************************
                       Gate
*********************************************************************************
******************************************************************************
*************************************************************************************
permision 
role
writer


بدنا نخلي الرايتر هو بس اللي يقدر ينزل بوستات


خش عل

providers\appserviceprovider

بنلاقي فنكشن اسمها
ريجستر بتكون فاضية

    public function register(): void
    {
        

        
    }




بتروح انتا بتحط جواتها هاض الحكي    Gate::define('create-post', function (User $user) {
            return $user->type == 'Writer';
        });

------------------------------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------------------------------------------------
انا هيك عملت الباب بس لسا ماركبتو


عشان اركبو بعمل التالي

بروح عمكان ال
button

اللي اسمها

blogs.create

مكتوب عليها 
add blog
موجودة بصفحة ال
blogs.index
وبخفي ال
button

    <div class="col-12 m-4">
        @can('create-post')

        <a href="{{ route('blogs.create') }}" class="btn btn-primary mt-5">Add New Blog</a>

        @endauth
        <center class="m-3">
            <h1>All Blogs</h1>
        </center>
    </div>




-------------------------------------------------
اذا دخل هون بدون صلاحيات اعطيه التالي
http://127.0.0.1:8000/blogs/create
403
This action is unauthorized.



عشان مايقدر يخش بدون راوت


    public function create(){

        Gate::authorize('create-post');
        $tags=Tag::select('id','name')->get();
        $categories = Category::all();
        $authors = Author::all();
        $users=User::select('id','name')->get();
        return view('blogs.add', compact('users','categories', 'authors','tags'));
    }



-----------------------------------------------------------------------------------
-----------------------------------------------------------------------------------
-------------------------------------------------------------------------------------------------
**************************************************************************************************************************************
****************************************************************************************************************************************
*****************************************************************************************************************************************
      policy
****************************************************************************************************************************************
*****************************************************************************************************************************************
*******************************************************************************************************************************************





