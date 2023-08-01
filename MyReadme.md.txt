-> We install express for our library, body-parser to process the request body, bcrypt for password encryption, cors for cross-origin requests, gridfs-stream for file upload, multer and multer-gridfs-storage so we acan upload our files locally, helmet for request safety, morgan for logging, jsonwebtoken for authentication, mongoose for mongodb access.

-> username - anshul02goyal, password = Bf2yKdHVEF0MfMhK

-> frontend running on port 3000 and backend running on 3001.

-> We have a route /auth/register and we are going to hit this route and from there we are going to upload this picture in locally public/assets folder and the register is the logic. 

-> jwt from jsonwebtoken will give a way to send a user a web token that they can use for authorization.

-> register = async(req, res) -> here async is like a api call from front end to back end then back into the database. It has a req(a request body) that we get from the front end and a response that we send to the front end. Express provides this by default.

-> register function => we are going to encrypt the password and we are going to save it and after we save it and when user enters the password, we are going to give them a json web token.

-> res.status(201) is for when a user is created.

-> ./routes/auth.js has the path and routes for every type of feature. routes/auth.js will allow Express to identify that these routes will be configured.

-> export const login => Here we take the email and password of the user and check in the database and if it is true, we sign the id using a JWT_SECRET and WE DELETE THE PASSWORD OF THE USER BECAUSE WE DO NOT WANT TO SEND IT BACK TO THE FRONT END. 

-> middleware/auth.js => we grab the authorization header from the front end and that's where the token will be set and then we verify the token.

-> There are 3 routes, one for the user i.e. we can see other user via id, second will be to see friendlist, third will be for adding and removing friends. In controllers/users.js we have created these 3 routes.

-> upload.single("picture") => when we upload an image on the front end, upload.single will grab the picture property. Here picture is the property and if the image is located there in the http call, then it will grab it and upload it in the local.

-> router.get("/", verifyToken, getFeedPosts) => this will provide all the posts on the homepage of the user that is present in the database.

-> router.get("/:userId/posts", verifyToken, getUserPosts) => this will provide all the posts that are relevant to user that you have selected.

-> In models/Post.js => we have created a model for the post and in likes: we have used a map with a value of boolean, basically it adds or removes the id of the user that has liked or disliked the post from the map.

-> In contollers/posts.js => id comes from query string and userId comes from body of the request.

-> browserRouter stores the current location in the browser's address bar using clean URLs.

-> state/index.js => it contains the state that will be stored in our Global state so this can be accessible throughout the entire app so that we don't have to pass in different State and properties down to different components. createSlice basically is a higher order function that contains slice name(auth), a set of reducers(functions) and returns a single function. Here state is the single state value that is managed by the store and action is the payload or a plain js object that contains info.

-> Redux persist is for storing of the user info or the initial state data into the local storage so that if the tabs are closed, info will be saved, only way to delete is clearing the cache.

-> const mode = useSelector((state) => state.mode) this will help us grab the value we created in our initial state. So if we ever want to grab info from the store we just have to use useSelector and grab the state in the correct reducer.

-> FlexBetween will have all those properties predefined and it uses material UI like Box components, so this allows us to pass any css property and use them as a component.

-> In loginPage/Form.jsx => yup is a javascript schema builder, parser, and validator. Basically if we put a symbol in string it will give error and there is required field. 

"& > div": {gridColumn: isNonMobile ? undefined : "span 4"}, => it means that add these properties below this div and if the view if of mobile then every grid will be of span 4, else it will be like previous.

Dropzone is a JavaScript library that turns any HTML element into a dropzone. This means that a user can drag and drop a file onto it, and Dropzone will display file previews and upload progress, and handle the upload for you via XHR.

-> In MyPostWidget.jsx => const [isImage, setIsImage] = useState(false) => this will represent the switch whether if someone has clicked the image button to open up a place to drop an image if they want to for the posting.

const [image, setImage] = useState(null) => this will be the actual image if they actually drop it.

const [post, setPost] = useState("") => this will represent the actual post content of description.