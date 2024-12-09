1. HTTP请求返回文件地址（如图片等），前端接口函数配置项要传responseType: "blob",拿到文件地址之后通过URL.createObjectURL生成url
```
export const getBannerAndFeatureImage = async () =>
	http.get(
		`xxx url`,
		{},
		{
			responseType: "blob",
		}
	);

const res = await getBannerAndFeatureImage();
const url = URL.createObjectURL(res.data);
```

2. HTTP请求上传图片文件
```
const profileFile = new File([customAvatarInfo], "profile.png", { type: "image/png" }); // 创建文件
const formData = new FormData();
formData.append("file", profileFile);
fileUpload(formData).then((res: any) => ...some logic // fileUpload是上传图片的API );
```
